The trendy way to denoise images with machine learning is to train GAN (like the well-known DeepArt) with a lot of examples. 
It will be very efficient for smartphone pictures, but very dangerous for scientific data as it can introduce structures from another dataset ; hallucinations. 
 
I use a deep convolutional network called DeepPior. https://github.com/DmitryUlyanov/deep-image-prior
This algorithm does not search for the answer in the image space like a trained GAN would do, it looks for the answer in the space of the neural network parameters. 
It is like a brain that trains itself to recreate that image without noise. 
There is no training, no apriori information so it’s safe for the data. It initialize an image randomly and it trains itself to recreate the original image. The only thing that it will never be able to recreate is random noise.
  
I propose 3 examples as 3 jupyter notebook adapted for astronomy. 
This is a very computing intensive process that requires a lot of GPU memory. With 16 Go of GPU memory you will only be able to denoise 1000 x 1000 images. It doesn't work on some GPU. I tested it on Tesla V100 and Tesla A100 with success. 
One solution could be to develop this algorithm for apple silicon and use a 128 Go unified memory Apple M3 max. Please contact me if you're able to adapt this algorithm to apple silicon.

One of these restorations has been published in NASA Astronomy Picture Of the Day : https://apod.nasa.gov/apod/ap240218.html


