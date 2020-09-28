# **Autoencoders**

An Autoencoder consists of two component, one is encoder and other is a decoder.

 **An encoder network that compresses high-dimensional input data into a lower-dimensional representation vector.**
 **A decoder network that decompresses a given representation vector back to the original domain.**

The network is trained to find weights for the encoder and decoder that minimize the loss between the original input and the reconstruction
of the input after it has passed through the encoder and decoder.

The representation vector is a compression of the original image into a lower-dimensional, latent space. The idea is that by choosing any point
in the latent space, we should be able to generate novel images by passing this point through the decoder, since the decoder has learned how to
convert points in the latent space into viable images.

[Autoencoders](Img/ae.png)

# **Variational Autoencoders**

In an autoencoder, each image is mapped directly to one point in the latent space. In a variational autoencoder, each image is instead mapped to
a multivariate normal distribution around a point in the latent space.

Variational autoencoders assume that there is no correlation between any of the dimensions in the latent space and therefore that the covariance 
matrix is diagonal. This means the encoder only needs to map each input to a mean vector and a variance vector and does not need to worry about 
covariance between dimensions. We also choose to map to the logarithm of the variance, as this can take any real number in the range (– ∞, ∞), 
matching the natural output range from a neural network unit, whereas variance values are always positive.

[Variational Autoencoders](Img/vae.png)


