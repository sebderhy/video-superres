# Video Enhancement
Video enhancement / super-resolution by transfer learning using fastai v1 library

## Idea
A video can be seen as a small dataset, so if we start with a good enough image enhancement model (in our case, we'll use [fastai lesson 7 model](https://github.com/fastai/course-v3/blob/master/nbs/dl1/lesson7-superres.ipynb) as a basis), and fine-tune it on the video itself, the model could then learn the specific of the recorded scene, and I hope very nice results can be achieved.

## How to run
The Notebooks [video-enhancement](https://github.com/sebderhy/video-enhancement/blob/master/video-enhancement.ipynb) and [video-enhancement-lite](https://github.com/sebderhy/video-enhancement/blob/master/video-enhancement-lite.ipynb) are basically doing the same thing. The lite one is just a version of the regular one without many debug cells.

These notebooks create automatically an enhanced video, as well as a comparions video to the input. However, in order to run, you will need to install ffmpeg, moviepy, and a few other things that are explained in the notebook.

## Open questions
* How can make the pictures' look more natural in general and remove the "overshooting" ? 
* Should we overfit in this specific case, since the test set IS the training set?
* How can we make the process fast enough so that it can be useful in real life? In particular, how can we make the learning as fast as possible? Also, currently, going from video to images and images to video takes a long time...

## Next steps
* Add an LSE term in the cost function 
* Try to use an RNN
* Any idea welcome !!

## Screenshots of Current Results 
Here are screenshots of results I've obtained so far on a test video
![res1](https://github.com/sebderhy/VideoEnhancement/blob/master/images/vid-enh-pic1.PNG "Comparison Image 1") 
![res2](https://github.com/sebderhy/VideoEnhancement/blob/master/images/vid-enh-pic2.PNG "Comparison Image 2") 
![res3](https://github.com/sebderhy/VideoEnhancement/blob/master/images/vid-enh-pic3.PNG "Comparison Image 3") 
![res4](https://github.com/sebderhy/VideoEnhancement/blob/master/images/vid-enh-pic4.PNG "Comparison Image 4") 
