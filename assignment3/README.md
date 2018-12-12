# Summary of Assianment 3
After learning for basic CNN knowledge, in this assignment more focus is on real computer vision application.

## Q1: Image Captioning using vanilla RNN and LSTM (pre-processed Microsoft COCO)
- We try to do auto image captioning using RNN, because of our no-fixed size of input and no-fixed size of output. Here although we talked about no-fixed size, we still assume a **maximum size limitation**. Also to deal with this problem, we have lots of parameters and you need to figure out what they exactly mean carefully. 

- Basic idea: we have an image feature vector and one caption of this image in the form of 2D matrix as input. 
<br>Image feature to `h0`, index captioning to `Vector captioning` and to use both to feed in RNN and compute loss.

## Q2: CNN Network Visualization (Based on Imagenet)
- Basic idea is the same: use pre-trained Squeezenet and do geadient descent on image pixels instead of parameters.
- Saliency Maps: visualize the gradient of correct class score on every image pixel
- Fooling Images: change the image class prediction without changing image pixel value a lot
- Class Visualization: generate an image which maximize certain class score.

## Q3: GANs
- Actually you can see this as an easy binary classification problem
- Two network: Generator & Discriminator
- Two loss: G_loss & D_loss to determine two network's capacity
- For network architecture and loss function, as many as you want

## Q4: Style Transfer (Squeezenet) 😂 Interesting but easy vision model
- Content loss: generate an image whose content should be similar to given content image's content using feature vector of Squeezenet
- Style loss: generate an image whose style should be similar to given style image's style using gram matrix
- tv_loss: regularization to generate a more smooth image

However, this assignment doesn't include segmmentation, object detection and reinforcement learning, the most difficult problems discussed in CS231N. It's a pity but from an assignment's view, it's wonderful and you can't acquire more. Especially for the last three Tensorflow (or Pytorch if you like) they are very good exercise for Tensorflow and I very recommand all of you to try.
