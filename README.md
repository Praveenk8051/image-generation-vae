# image-generation-vae
Image Generation Using the Variational Autoencoder

### [Project Code](https://github.com/Praveenk8051/image-generation-vae/blob/main/vae_generative_models) - (_ipynb format_)


### ***Description***


In the variational autoencoder, the bottleneck vector is replaced by 2 separate vectors mean of the distribution and standard deviation error of the distribution.  So whenever data is fed into the decoder, samples of the distribution is passed through the decoder. The loss function of variational autoencoder consists of 2 terms. First one is the reconstrcution loss, it is same as the autoencoder expect we have expectation term because we are sampling from the distribution. The second term is the KL divergence term. The second term ensures that it stays within the normal distribution. We basically train to keep the latent space close to mean of 0 and standard deviation of 1 which is equivalent to normal distribution

* **Loss Function**

The Gradients are pushed and samed latent vector is trained using **reparameterization trick**.

So the trick goes as follows, if you see the latent vector then it can be seen as the sum of the _mu_, which is the parameter you are learning, _sigma_ which is also the parameter we are learning and multiplied by _epsilon_, this _epsilon_ is where we put the stochastic part. This _epsilon_ is always gonna be guassian with zero mean and standard deviation of 1. So the process is we gonna sample from _epsilon_, multiplied by _sigma_ and add it with _mu_ to have latent vector. So _mu_ and _sigma_ are the only things we have to train and it would be possible to push the gradients to decrease the error and train the network. The _epsilon_, is ok not to be trained. We need the stochasticity which would help us in generating the images

* **Reparameterization trick**

![image](/images/reparameter.png)


The summarised version of the block diagram and sampled latent representation can given as below.

* **Summarised Block Diagram**


![image](/images/summarised.png)

### ***Training***
![image](/images/training.png)



### ***Results - Generated Images***
![image](/images/generated_images.png)