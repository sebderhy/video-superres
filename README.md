# Video Enhancement
Video enhancement by transfer learning using fastai v1 library

## Idea
A video can be seen as a small dataset, so if we start with a good enough image enhancement model (in our case, we'll use [fastai lesson 7 model](https://github.com/fastai/course-v3/blob/master/nbs/dl1/lesson7-superres.ipynb) as a basis), and fine-tune it on the video itself (for once, overfitting could be good !!), the model could then learn the specific of the recorded scene, and I hope very nice results can be achieved.

## Current Results
Here are screenshots of results I've obtained so far
![res1](https://github.com/sebderhy/video-enhancement/blob/master/images/vid-enh-pic1.PNG "Comparison Image 1") 
![res2](https://github.com/sebderhy/video-enhancement/blob/master/images/vid-enh-pic2.PNG "Comparison Image 2") 
![res3](https://github.com/sebderhy/video-enhancement/blob/master/images/vid-enh-pic3.PNG "Comparison Image 3") 
![res4](https://github.com/sebderhy/video-enhancement/blob/master/images/vid-enh-pic4.PNG "Comparison Image 4") 

## How to run
The Notebooks [video-enhancement](https://github.com/sebderhy/video-enhancement/blob/master/video-enhancement.ipynb) and [video-enhancement-lite](https://github.com/sebderhy/video-enhancement/blob/master/video-enhancement-lite.ipynb) are basically doing the same thing. The lite one is just a version of the regular one without many debug cells.

These notebooks create automatically an enhanced video, as well as a comparions video to the input. However, in order to run, you will need to install ffmpeg, moviepy, and a few other things that are explained in the notebook.

## Open questions
* How can I fix the overshooting effect and make the video feel more natural? Maybe add a LSE term in the cost function?
* Should we overfit or not?
* How can we make the algorithm fast enough so that it can be productionized? In particular, how can we make the learning as fast as possible? Also, currently, even when the model is trained, writing the output images still takes a long time.
