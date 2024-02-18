#  I. Introduction 

>  Matlab is getting better and better, and the latest version of Matlab (2022b) has provided relevant functions for extracting ISS keypoints, which are still very useful. I will also use them here (for non-built-in functions, please refer to: Matlab ISS Keypoints). 

>  The full name of ISS is Intrinsic Shape Signatures. It is a three-dimensional shape descriptor. This descriptor is mainly used to describe the characteristics of the local/semi-local area of the point cloud, which is convenient for subsequent registration and other processes. The calculation process is mainly divided into two steps: 1. First, based on the point 

          p 

         p 

     P and its neighbors create a local coordinate system whose axes are the three eigenvectors of the covariance matrix in the following equation. 

![avatar]( a6b6e6c4378b49988e33f983063352ff.png) 

>  2. Determine whether the point is an ISS feature point according to the obtained eigenvalues. The judgment conditions are as follows: 

![avatar]( f31274de6e794833ac5d6b99ea8351cd.png) 

>  The basic principle is to avoid the detection of key points at points that exhibit similar diffusion along the main direction, because it is impossible to establish a repeatable standard reference frame at these points, which makes it difficult to effectively explain these points later. The simple point is that if it is a corner, the three eigenvalues will not be too different, and if it is a boundary line, there will be one eigenvalue much larger than the remaining two. In addition to the above two cases, the significance of the remaining points is determined by the size of the minimum eigenvalue, so as to include only the points with large changes in each main direction. Finally, after the detection step is completed, a point is considered critical if it has the largest significance value in a given neighborhood (non-maximum suppression is used here to obtain a local maximum). 

#  Implementation code 

The relevant parameter settings can be read in detail in the comments section of the code. 

>  ISS.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574059741
 ```  
#  III. Achieving results 

![avatar]( 4d0f89d6c3f740b489d5bf94b518e752.png) 

#  reference 

>  [1]Intrinsic Shape Signatures: A Shape Descriptor for 3D Object Recognition [2]Matlab帮助文档 

