# Video Enhancement
Video enhancement / super-resolution by transfer learning using fastai v1 library

## Idea
The idea is that since a video is a small dataset, if we start with a good image enhancement model (in my case [fastai lesson 7 "pets" model](https://github.com/fastai/course-v3/blob/master/nbs/dl1/lesson7-superres.ipynb)), and fine-tune it on the images of the video, the model can hopefully learn specific details of the scene when the camera gets closer and then reintegrate those details back when the camera gets further away.

## How to run
The notebook [video-enhancement](https://github.com/sebderhy/video-enhancement/blob/master/video-enhancement.ipynb) does the learning, then create the enhanced video, and then compare the enhanced video against the input and/or an intermediate "milestone" (basically the benchmark result we are trying to beat). However, in order to run, you will need to install ffmpeg, moviepy, and a few other things that are explained in the notebook.

## MSE Vs Feat Loss
I noticed that the feature loss had a tendancy to create over-sharpening issues, so I added the option to couple an MSE loss and the feature loss.

## Open questions
* Should we overfit in this specific case, since the test set IS the training set?
* How can we make the process fast enough so that it can be useful in real life? In particular, how can we make the learning as fast as possible? Also, currently, going from video to images and images to video takes a long time...

## Next steps
* Try to use an RNN ?
* Any idea is welcome !!

## Results and comparison to [fastai lesson 7 model](https://github.com/fastai/course-v3/blob/master/nbs/dl1/lesson7-superres.ipynb)
*Notice how the new model fixes the checkerboard issue that we obtain with the "pets" (fastai lesson 7) model*

### Example input image:
![input1](https://github.com/sebderhy/VideoEnhancement/blob/master/github-images/input-images-1.png "Input Image 1") 

### Result from [fastai lesson 7 model](https://github.com/fastai/course-v3/blob/master/nbs/dl1/lesson7-superres.ipynb)
![enh-pets-1](https://github.com/sebderhy/VideoEnhancement/blob/master/github-images/enh-pets-1.png "Pets model result 1") 

### Results from this model
![new-res-1](https://github.com/sebderhy/VideoEnhancement/blob/master/github-images/enh-ftlss-only-mstn1-1.png "New model result 1") 
