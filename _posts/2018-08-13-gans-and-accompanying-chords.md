---
layout: post
title:  "GANs and Accompanying Chords"
date:   2018-08-13 18:46:00
categories: GANs Max
---

In the past weeks, we utilized different technologies to make progress on both visual and aural presentations. Regarding the visual aspects, the main breakthrough was engaging generative adversarial networks (GANs) to create new unique images based on the visualizations that we created by using dimensionality techniques such as t-SNE.

![t-SNE visualization](/assets/images/tsne.gif)

The above visualization is one example of t-SNE visualizations from our training sets. This visualization has a finite number of images, so it loops over at a certain point. However, by using GANs, we can generate new images as shown below.

![GAN learning to produce new images](https://lh6.googleusercontent.com/WKtg6N2wyf6QC_jysaYG5RwdYEw6m0dfJ2mCDzNUFo6FBpw_Sxi3OLVFQ6ECnanTA_wWICLdFm7twP8mIhQrBUii2hfbg-E4NhbSzHGFz89IBx-uq6Bltx7ALxrU7lAG45Kl_UUa)

At each learning step, the network learns to lower the error rate and produce more accurate images according to the training images. It starts with static images as the model’s understanding of how to create images is limited in the beginning and at later stages, the images look more similar to the training set. Furthermore, by including more images in the training set, we can create visualizations in different flavors.

| Snowflakes  | Fireworks | 
| :-------------: | :-------------: |
| <img src="https://lh5.googleusercontent.com/l5Gr70eKhmNhWhzDgsIynsQtI2WK9ypr1BgJpyASojjceVYmjtPyct2vJzMEBF7GBEKvyajcmPQUCAKeJ3Am_g2A8gIcWbdUeY8FYdyh80sOyMkD9Gk4DtBWpJXxDqx9NhIwGdcD" width="50%"> | <img src="https://lh3.googleusercontent.com/w2UVQbcvaeatlYAlsJvFVebUtox968l8JOeRv5t8pPoRhM41npRIAExXVOW4PPtb1gNtbW0T4e-thqYXtZw4m8dyKSSJ2PS9Y9TudGdQEP6jVKGmgCULhQh7ZxrL86KewE2N0UVI" width="50%">

The challenge with this technique is that using images makes the training computationally expensive as each pixel value is used as a feature. So far, we created images in small dimensions to reduce the training time as much as possible. In the coming weeks, we plan to produce high fidelity images with colors and better resolutions using the same technique.

In the world of Max, we used the t-SNE gif of morphing points as an example to explore what the movements could sound like. The result is [here](https://drive.google.com/file/d/12bjvJvAdYFN1zg29FCeLnjBw1QQKNIdD/view?usp=sharing) - a wave of changing three-note chords that move with the points. The process we designed for directing pure images/videos to sounds is inspired by [12-tone temperament](https://en.wikipedia.org/wiki/Equal_temperament#Twelve-tone_equal_temperament), a tuning method where one divides the frequencies of a scale into 12 half steps equally. Similarly, we looked at each frame of the video and drew 12 virtual circles around the center equally spaced. Depending on where the points fall into those 12 spaces, certain sounds would be triggered. In fact, each space represented a half note; we used C4 as a base note, so each frame could possibly trigger sounds from C4 to C5. Next, since there are hundreds of points in each frame, if we let each point trigger a note, it would sound like piano slamming. Instead, we took three points from each frame for sound generation, specifically, the furthest point from the center, the closest point from the center, and a midpoint. This way, what we hear is a series of chords - what we are used to hearing - represented by the general movements of the morphing points.

During the meeting, we presented these visual and aural examples to the team and we all agreed that we’ve made significant progress in the concept and the artistic representation space. Next, it’s time to think about the material with which we will realize these concepts, while creating more of these visual and aural examples.
