# Affine Transformation of Virtual Object
A convolutional neural network (CNN) based thumb and index fingertip detection system are presented here for seamless interaction with a virtual 3D object in the virtual environment. First, a two-stage CNN is employed to detect the hand and fingertips and using the information of the fingertip position, the scale, rotation, translation, and in general, the affine transformation of the virtual object is performed.

## Update 
This is the version ```2.0``` that includes a more generalized affine transformation of virtual objects in the virtual environment with more experimentation and analysis. Previous versions only include the geometric transformation of a virtual 3D object with respect to a finger gesture. To get the previous versions visit [here](https://github.com/MahmudulAlam/Fingertip-Mixed-Reality/releases). 

[![GitHub stars](https://img.shields.io/github/stars/MahmudulAlam/Fingertip-Mixed-Reality)](https://github.com/MahmudulAlam/Fingertip-Mixed-Reality/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/MahmudulAlam/Fingertip-Mixed-Reality)](https://github.com/MahmudulAlam/Fingertip-Mixed-Reality/network)
[![Downloads](https://img.shields.io/badge/version-2.0-orange.svg?longCache=true&style=flat)](https://github.com/MahmudulAlam/Fingertip-Mixed-Reality)
[![GitHub license](https://img.shields.io/github/license/MahmudulAlam/Fingertip-Mixed-Reality)](https://github.com/MahmudulAlam/Fingertip-Mixed-Reality/blob/master/LICENSE)

## Paper

[![Paper](https://img.shields.io/badge/paper-IeeeXplore-blue.svg?longCache=true&style=flat)](https://ieeexplore.ieee.org/abstract/document/9035256)

Paper for geometric transformation of the virtual object [```v1.0```](https://github.com/MahmudulAlam/Fingertip-Mixed-Reality/releases/tag/v1.0) has been published. For more detail, please go through the [paper](https://ieeexplore.ieee.org/abstract/document/9035256). Cite the paper as: 
```
@inproceedings{alam2019detection,
  title={Detection and Tracking of Fingertips for Geometric Transformation of Objects in Virtual Environment},
  author={Alam, Mohammad Mahmudul and Rahman, SM Mahbubur},
  booktitle={2019 IEEE/ACS 16th International Conference on Computer Systems and Applications (AICCSA)},
  pages={1--8},
  year={2019},
  organization={IEEE}
}
```

## System Overview
Here it the real-time demo of the scale, rotation, translation, and overall affine transformation of the virtual object using finger 
interaction.

<p align="center">
  <img src="https://user-images.githubusercontent.com/37298971/78501859-96a26b00-777f-11ea-9f33-977ea8feda09.gif" width="640">
</p>

<!---
<pre>
  <strong>                scale transformation                                  rotation transformation   </strong>
</pre>
<p align="center">
  <img src="https://user-images.githubusercontent.com/37298971/75994594-6881ff00-5f25-11ea-9194-ac44a082dcc6.gif" title="scale transformation" width="400" />
  <img src="https://user-images.githubusercontent.com/37298971/75994991-f958da80-5f25-11ea-9db3-0bc079f5e687.gif" title="rotation transformation" width="400" />
</p>
<pre>
  <strong>             translation transformation                                 affine transformation   </strong>
</pre>
<p align="center">
  <img src="https://user-images.githubusercontent.com/37298971/75995017-0249ac00-5f26-11ea-91ea-2a19a63384ca.gif" title="translation transformation" width="400" />
  <img src="https://user-images.githubusercontent.com/37298971/75995036-0675c980-5f26-11ea-967a-10b9fe45853d.gif" title="affine transformation"width="400" />
</p>
-->

## Dataset
To train the hand and fingertip detection model two different datasets are used. One is a self-made publicly released dataset called [TI1K Dataset](https://github.com/MahmudulAlam/TI1K-Dataset) which contains 1000 images with the annotations of hand and fingertip position and another one is [Scut-Ego-Gesture Dataset](http://www.hcii-lab.net/data/SCUTEgoGesture/index.htm). 

## Requirements
- [x] TensorFlow-GPU==1.15.0
- [x] OpenCV==4.2.0
- [x] Cython==0.29.2
- [x] ImgAug==0.2.6
- [x] Weights: [```download```](https://mega.nz/folder/SkklxRAA#Z0p60mPe1BwJ7ZTZniMtDA) the trained weights file for both hand and fingertip detection model and put the weights folder in the working directory. 

[![Downloads](https://img.shields.io/badge/download-weights-blue.svg?style=popout-flat&logo=mega)](https://mega.nz/folder/SkklxRAA#Z0p60mPe1BwJ7ZTZniMtDA)

## Experimental Setup
The experimental setup has a server and client-side. Fingertip detection and tracking and all other machine learning stuff are programmed in the server-side using Python. In the client-side, the virtual environment is created using Unity along with Vuforia software development kit (SDK). To locate and track a virtual object using the webcam, Vuforia needs marker assistance. For that purpose, a marker is designed which works as an image target. The [```marker/```](https://github.com/MahmudulAlam/Fingertip-Mixed-Reality/tree/master/marker) folder contains the pdf of the designed marker. To use the system print a copy of the marker.

<p align="center">
  <img src="https://user-images.githubusercontent.com/37298971/57572552-c9dc5d00-743d-11e9-9f1c-fcf9d97517b5.jpg" width="800">
</p>

## How to Use
First, to run the server-side directly run ```'server.py'```. It will wait until the client-side (Unity) is starting to send images to the server. 
```
directory > python server_track.py
```

<p align="center">
  <img src="https://user-images.githubusercontent.com/37298971/57572729-97802f00-7440-11e9-9c5c-fa4d6427d8ec.png" width="700">
</p>

Open the ```'Unity Affine Transformation'``` environment using [```Unity```](https://unity3d.com/get-unity/download) and hit the play button. Make sure a webcam is connected. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/37298971/57572793-5b010300-7441-11e9-96cb-07bec8f818b1.png" width="700">
</p>

Bring your hand in front of the webcam and interact with the virtual object using your finger gesture.

<!---
## Demo
<p align="center">
  <img src="https://user-images.githubusercontent.com/37298971/60720908-07e19300-9f4e-11e9-8e38-f322d81a9abd.gif" width="700">
</p>
-->
