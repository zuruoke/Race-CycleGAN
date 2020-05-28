# Race-CycleGAN
Using the Powerful CycleGAN to translate image of different races from one race to another
Generative Adversarial Network (GAN) is the most interesting idea in the last 10 years quoted by Yann LeCun, regarded as the father of Convolutional Network

There are many variants of GANs including: Pix2PixGAN, InfoGAN, CycleGAN, StarGAN, Nvidia-backed StyleGAN etc. 
I will adopt the CycleGAN.


So let's talk a little about the CycleGAN

CycleGAN performs image translation, that is, it transforms an image in a given domain to another domain. 

The CycleGAN performs this image translation in absence of training pairs - it just learns the mappings between each domain and creates resemblence of the image relative to the domains

The ability to perform image translation with unpaired data makes it so powerful, unique and robust as most conditional GANs deal with paired data, e.g Pix2Pix



In order to accomplish image translation in absence of training pairs, CycleGAN introduces two (2) Discriminators & two (2) Generators with three losses losses associated with each of them:
- Forward Cycle Consistency Loss
- Backward Cycle Consistency Loss
- Identity Loss

![cycle_loss](https://user-images.githubusercontent.com/51057490/83192850-056fc500-a12e-11ea-9118-01417ead05ca.png)

In this project I'll adopt a powerful variant of GAN called [CycleGAN](https://arxiv.org/pdf/1703.10593.pdf) to build a model that can translate an image of a Negroid to a Mongoloid resemblance and vice-versa

- Mongoloid: includes people of Asian descent, especially Eastern Asian 
 
- Negroid: includes people of African descent or black Americans

All 30,254 images was aggregated from [LFW](http://vis-www.cs.umass.edu/lfw/) and [Flickr](https://www.flickr.com/)

The Workflow for this kernel:

- Build an Input Data Pipeline for the Image preprocessing
- Build the two (2) Discriminator Model which introduces a PatchGAN
- Build the two (2) Generator Model inclusive of a bottleneck (Transformer)
- Configure the various Loss functions and set equitable hyperparameters λ
- Train the Model - first train the disriminators, freeze it and then train the generators 
- Create an Inference Graph to test the model

# RESULTS

![g11](https://user-images.githubusercontent.com/51057490/83197329-3acbe100-a135-11ea-8192-88963453c751.JPG)

![17](https://user-images.githubusercontent.com/51057490/83197476-723a8d80-a135-11ea-981a-0c3a73f452fa.JPG)
![zre](https://user-images.githubusercontent.com/51057490/83197429-5e8f2700-a135-11ea-9c7b-b5440dd41ac3.JPG)

# CONCLUSION

The Resultant Images are kind of distorted because of the amount of training images used, hence I'll recommend [Nvidia StyleGAN](https://arxiv.org/pdf/1812.04948.pdf) for this kind of task with large amount of Images  
