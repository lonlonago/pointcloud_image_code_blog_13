#  I. Introduction 

>  The approximate process of the FPS algorithm can be found in the previous article: MATLAB Farthest Point Sampling (FPS), but it is easy to find that in the process of (2) of this method, there are a large number of distance calculation operations, and as the number of sampling points increases, the amount of calculation will also increase a lot. The specific growth method is based on polynomials 

          O 

          ( 

          n 

          ∗ 

          ( 

          n 

          − 

          k 

          ) 

          ) 

         O(n*(n-k)) 

     O (n * (n − k)) mode growth, after selecting the first 

          n 

          / 

          2 

         n/2 

     When n/2 sampling points, the computation amount reaches the maximum 

          ( 

           n 

           2 

          ) 

          / 

          2 

         (n^2)/2 

     (N2)/2. But in fact, the main reason for updating the minimum distance from the remaining points to the selected points every time is the addition of the new selected points last time, because the addition of this new point makes all the unselected points need to be updated, but obviously this update does not require the previous sampling points to calculate the distance again, so there is a lot of repetition. Therefore, if this new point is calculated with the distance from all the remaining points, and this distance is compared with the distance value saved before the new point, then the amount of calculation can be greatly reduced, so that the method's speed of picking points on the number of currently commonly used point clouds can be improved, which can be reduced to 

          O 

          ( 

          k 

          n 

          ) 

         O (kn) 

     O (kn), but if the amount of data is large and there are many options, it is actually still 

          O 

          ( 

           n 

           2 

          ) 

         O(n^2) 

     O(n2)。 

#  Implementation code 

>  FPSV1.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574029242
 ```  
#  III. Achieving results 

![avatar]( c15272f7e27c4a53ab1ae120e0a21f64.png) 

 ![avatar]( 05d40baa78c4403ebc182fdf4b1cb6ef.png) 

#  reference 

>  [1]https://blog.csdn.net/qq_36265860/article/details/114067220 



--------------------------------------------------------------------------------

#  I. Introduction 

>  In short, this method selects the point farthest from the previous point set by iterative and incremental means to realize the data sampling process. The algorithm steps are as follows: 

![avatar]( 9711abc2752647d3833dabe9bf0be555.png) 

>  (1) From the point set 

          S 

         S 

     randomly select a point in S 

           p 

           i 

         p_i 

     Pi as sample point set 

          X 

         X 

     The first point in X. (2) Compute the distance between the remaining points and the set of sampling points (i.e. each remaining point to the set of sampling points) 

          X 

         X 

     The shortest distance of X), choose the distance from it 

          X 

         X 

     X largest point 

           p 

           j 

         p_j 

     PJ as the new sampling point and add it to 

          X 

         X 

     In X. (3) Repeat the process of (2) until the number of sampling points reaches the requirements set by us, then the sampling process can be stopped. 

Here we implement a version 2 of the FPS algorithm. 

#  Implementation code 

>  FPS_2D.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574029517
 ```  
#  III. Achieving results 

![avatar]( 7b3fac994c4c453c92333365dc734625.png) 

#  reference 

>  [1MATLAB farthest point sampling (FPS improved version) ] 



--------------------------------------------------------------------------------

#  I. Introduction 

>  ICP registration and color point cloud registration are both called local registration methods because they both rely on rough alignment for initialization. Algorithms like global registration do not require initialization for alignment, but they usually produce less tightly aligned results and are used as initializers for local methods. FGR is such an algorithm, and the entire algorithm flow is as follows: 

![avatar]( 3cf2b61562144c8393da832f7909fd7b.png) 

#  Implementation code 

First, we need to download the source code of FGR (see Resources for the URL), and then we need to use cmake to generate the vs project, as follows: 

![avatar]( da7e7d5f952a47ddba49bf74c2400792.png) 

 Finally, generate the corresponding mexw64 file. 

![avatar]( 15e6da8e177c48fcb46fba0922f3e189.png) 

 ![avatar]( 64c3727cdf6a44d2bfc93fc4c453779b.png) 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574099295
 ```  
#  III. Achieving results 

![avatar]( a0c8b0b8af264c8c8919ba0d8e664845.png) 

#  reference 

>  [1]http://www.open3d.org/docs/release/tutorial/pipelines/global_registration.html [2]Fast Global Registration [3]https://github.com/isl-org/FastGlobalRegistration 



--------------------------------------------------------------------------------

#  I. Introduction 

>  The canopy density is the percentage of the forest area that the vertical projection of the canopy of the stand accounts for. In forest management, canopy density is an important indicator to determine the intensity of tending and harvesting, and it is also an indispensable factor for forest stock estimation. The calculation process is also relatively simple, that is, for a statistical unit, canopy density can be calculated as the ratio of vegetation points to the total number of points. Similar to the calculation of clearance rate, points greater than the height threshold in the calculation process can be considered as vegetation points. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574095831
 ```  
#  III. Achieving results 

![avatar]( f356c46b13a54e06b2e39237dde498d7.png) 

 ![avatar]( a31d77716c2a40e18c56fd6bb7970ae2.png) 

#  reference 

>  [1]https://www.lidar360.com/wp-content/LiDAR360-zh/ToolReference/ALSForest/TheoryOfCanopyCover.html 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Gap rate refers to the death of old trees in forest communities or the death of dominant tree species in the mature stage due to accidental factors, resulting in gaps in the forest canopy. The calculation formula is simple after all, that is, the ratio of ground points to the total number of forest points. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574082991
 ```  
#  III. Achieving results 

![avatar]( 03f402d33a44409a8fb8c25a909979e8.png) 

 ![avatar]( f0cf3511621c4cc6b1f759f47bd99695.png) 

#  reference 

>  [1]https://www.lidar360.com/wp-content/LiDAR360-zh/ToolReference/ALSForest/TheoryOfGapFraction.html 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Matlab is a little strange, there is no method to extract PFH features, but there is a method to extract FPFH (Fast Point Feature Histograms) features. For the details of PFH, you can see this paper: Semantic 3D Object Maps for Everyday Manipulation in Human Living Environments or this article https://pcl.readthedocs.io/projects/tutorials/en/latest/pfh_estimation.html#pfh-estimation. It not only describes the characteristics of PFH, but also describes the advantages of FPFH features. In general, compared with ordinary normal vector and curvature features, FPFH can better describe the geometric features around each point. Compared with PFH features, it can improve the computing speed while ensuring the capture of surrounding features as much as possible, which makes this feature can be used in some real-time application scenarios with high requirements. 

#  Implementation code 

>  FPFH.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574038009
 ```  
>  More detailed parameter settings can be found in the help documentation in MATLAB (select the function name and press F1). 

#  III. Achieving results 

![avatar]( 2d9bda56a14b47c89919e176f9b07061.png) 

>  It can be clearly seen that the FPFH feature histograms of the corresponding matching points in the two point clouds are very similar. 

![avatar]( 0ee4d5bcf859459c9c02736da284b2b7.png) 

#  References 

>  [1]Semantic 3D Object Maps for Everyday Manipulation in Human Living Environments [2]https://pcl.readthedocs.io/projects/tutorials/en/latest/pfh_estimation.html#pfh-estimation [3]Matlab帮助文档 



--------------------------------------------------------------------------------

#  Overview of the principle 

>  In order to obtain the DBH of a single tree more stably and accurately, referring to some methods in the literature, a sharding cutting method is used to obtain its size. The approximate process can be divided into the following steps: (1) First, the extracted trunk point cloud is stratified and sliced. (2) The slices are projected to the horizontal plane, and a circle is fitted by using the RANSAC algorithm. (3) Connect the fitted centers of each layer to obtain a curve, which can be smoothed. (4) Refit the center of the circle obtained after smoothing to obtain a more accurate DBH size. 

#  Implementation code 

>  SliceBreast.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574078288
 ```  
>  RANSACCircle.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574078288
 ```  
>  OLSCircle.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574078288
 ```  
>  DrawCircle.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574078288
 ```  
#  III. Achieving results 

![avatar]( 39a110e145d34ce5856b5880421679a3.png) 

>  It can be seen that the smoothed curve is much more realistic, and on this basis, a more accurate single wood DBH can be obtained. 

![avatar]( 3681f2351f754dd7848db41a3546f37d.png) 

#  References 

>  [1]Measuring stem diameters with TLS in boreal forests by complementary ftting procedure 



--------------------------------------------------------------------------------

#  Overview of the principle 

>  The specific principles have been implemented in the ICP code in the previous article, and I will not say more here. The following mainly uses the pcregistericp function in MATLAB to implement the ICP registration function. 

#  Implementation code 

>  ICPV5.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574099280
 ```  
#  III. Achieving results 

>  InlierRatio = 0.1 

![avatar]( 677fc8ee8b42445a9ec4698b514c7b6e.png) 

>  InlierRatio = 0.5 

![avatar]( 29d37ca0197e4bedaa65fdb2825dd4a4.png) 

>  InlierRatio = 1 

![avatar]( d677fe54e80842c1847a2eda99e8da3f.png) 

>  From the above figure, it can be seen that the smaller the proportion of matching points selected, the more prone it is to local optimality, which makes the registration effect less than ideal. Therefore, the actual situation still needs to be actually analyzed. However, if it is to deal with the registration problem of a larger data set, it is generally necessary to downsample first, and then calculate the optimal conversion matrix, which can greatly reduce the registration time. The specific code is shown below. 

>  ICPV4.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574099280
 ```  
#  reference 

>  [1] Matlab help documentation (select the function name in MATLAB and press F1) 



--------------------------------------------------------------------------------

#  I. Introduction 

>  The main idea here is to use the FPS algorithm to choose as many seed points as possible, and these seed points will be used as the initial centroid points of the kmeans algorithm to optimize the kmeans algorithm. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574093276
 ```  
#  III. Achieving results 

![avatar]( c13be19e2e3d4312bfa84d3ce261cbb9.png) 

 ![avatar]( 64f49b9be3904a7493555a9d4efa7113.png) 

#  reference 

>  [1] Matlab farthest point sampling (FPS, 2D version) 



--------------------------------------------------------------------------------

#  Overview of the principle 

>  The basic principle of the inflection point method of adaptive k value can be described as follows: as the number of target clusters increases, the number of samples in the target cluster set gradually decreases, and the distance between the samples and the center of the cluster is closer, the J value of the objective function also becomes smaller. When the number of target clusters is greater than the optimal number of classes k, the subset of clusters is formed by merging multiple clusters into a single cluster split. At this time, the objective function J suddenly becomes smaller and keeps slowing down. Therefore, by setting different target class numbers to calculate the objective function J value and plotting the cluster number-objective function curve, the k value corresponding to the inflection point (mutation point) of the objective function curve is the optimal number of target cluster classes. 

#  Implementation code 

>  InflectionPointMethod.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574085991
 ```  
#  III. Achieving results 

![avatar]( 1485fdc98d6742929f7121638ba13d37.png) 

>  According to the ideas in the paper to test the method, the test effect is not very ideal, because the original data source is roughly 8 categories, but the best k value detected by this method should be 5 categories, and further research is needed later. 

#  References 

>  [1] Research on key technologies for inspection of airborne laser point cloud transmission lines 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  I. Introduction 

>  Through the normal vector of each side of the convex polygon, the visibility of the polygon compared to a certain point can be judged. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957403337
 ```  
#  III. Achieving results 

![avatar]( 9bab5ad8e3b34d5eac0fad507bfa54d4.png) 

#  reference 

>  [1]Geometric Tools for Computer Graphics 



--------------------------------------------------------------------------------

#  I. Introduction 

##  1.1 Fitting plane by least squares method 

>  Previously, we used the most classic method to fit the plane in least squares (point cloud least squares method to fit the plane). The derivation process is as follows: 

![avatar]( 7318bf2cd65545e687e6815cd134bd55.png) 

 ![avatar]( 44cf5e00075948a8b4f3b1c5a402b54f.png) 

 ![avatar]( 25ec4278e2764a83929073e54c27969c.png) 

 A closer look reveals that 

          Q 

         Q 

     Q is actually the covariance matrix of the coordinates, and it can be found by inverting it 

          X 

         X 

     X solution. 

##  1.2 SVD angle 

>  However, if we change our perspective, we can obtain another solution. We all know that the eigenvalues of a matrix have this property: 

>  If all the above coordinates are decentrified, i.e. 

          ( 

           x 

           i 

          , 

           y 

           i 

          , 

           z 

           i 

          ) 

          − 

          ( 

           x 

           ^ 

          , 

           y 

           ^ 

          , 

           z 

           ^ 

          ) 

         (x_i,y_i,z_i)-(\hat x,\hat y,\hat z) 

     (Xi, yi, zi) − (x ^, y ^, z ^), then (4) can be changed to: 

>  At this point, let's take a look at this form again. 

           Q 

           ′ 

          X 

         Q'X 

     Q ′ X is actually the residual from the point to the plane, if it is equal to 0, then the 

          X 

         X 

     X is the optimal solution, but we all know that often problems with noise points cannot make the residuals 0, so our actual goal is actually: 

>  Thinking about the above properties, we come to the conclusion that: 

>  that is 

           Q 

           ′ 

         Q' 

     Q ′ matrix 

           i 

            m 

            i 

            n 

         \lambda_{min} 

     When λ min, the corresponding eigenvector is the optimal solution we want 

          X 

         X 

     X, so we can use the SVD algorithm to solve for 

          X 

         X 

     X solution ( 

          a 

          , 

          b 

          , 

          c 

         a,b,c 

     A, b, c coefficients), and we decentrified before, so we can get it from the centroid point 

          d 

         d 

     d。 

Note: This is just for ease of understanding, intuitive analysis from the perspective of SVD, and more rigorous forms require private mathematical derivation. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574068313
 ```  
>  DrawPlane.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574068313
 ```  
#  III. Achieving results 

![avatar]( cc8a27fbc1244d96bb489036e4eae6b2.png) 

 ![avatar]( 0f7d234c9fa34a0e9393d59e5bfb51e5.png) 

#  reference 

>  [1] Point cloud least squares fitting plane 



--------------------------------------------------------------------------------

#  I. Introduction 

The Matlab version is 2022b. 

>  The method first calculates the curvature of each point using the nearest neighbor of the point in the same laser scan, and then detects the lidar odometry and mapping (LOAM, lidar odometry and mapping) feature in the point cloud based on the curvature value of each point. Where the curvature value of the feature point determines whether the function classifies it as a sharp-edged, not-very-sharp-edged, flat-curved, or not-quite-flat-surface point, and thus classifies each point. (This algorithm is only suitable for ordered point clouds) 

#  Implementation code 

>  loam.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574048857
 ```  
#  III. Achieving results 

![avatar]( 281a0f2a3d2a4ec0989e97020e328023.png) 

#  reference 

>  [1] Matlab Help Documentation 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Purely out of curiosity, I found a book to learn about the implementation of spline functions, as follows: 

Derivation process: 

![avatar]( 52765418b94946d5baa8cdd046a95801.png) 

 ![avatar]( 5dd9bc0374004414906c0b595d58f7ff.png) 

 ![avatar]( b85aca8d17904e4492252e165841071d.png) 

 Algorithm flow: 

![avatar]( d00c4510f955477f8e80c81321f01e0e.png) 

 ![avatar]( 7013d70e899f43f983ec6cde71919678.png) 

>  In the above 

          l 

          、 

          u 

         l、u 

     L and u are the upper and lower triangular matrices of the coefficient matrix, respectively, and the algorithm flow here only constrains the second derivative of the two ends to 0, without adding more constraints. For more details, please refer to the references at the end of the article. 

#  Implementation code 

>  splinefunc.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574097890
 ```  
#  III. Achieving results 

![avatar]( 2030fedbc158437089caaa34f789ed59.png) 

>  From the perspective of the implementation, the derivation of the formula and the algorithm flow are completely ok. 

#  References 

>  [1]《Numerical Analysis-Burden Faires 9th》 



--------------------------------------------------------------------------------

#  I. Introduction 

>  The process for generating a spline function with slope constraints at both ends is as follows: 

![avatar]( 6cb5f8b931d54a188f54e9362f85587a.png) 

 ![avatar]( 085b5e416cac49ffa0bf1620a5096ed9.png) 

#  Test code 

>  splinefuncv1.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957405595
 ```  
#  III. Achieving results 

![avatar]( ff21c669c61d48499de83b9ec0b0ac9d.png) 

#  References 

>  [1]《Numerical Analysis-Burden Faires 9th》 



--------------------------------------------------------------------------------

#  Overview of the principle 

>  The normal distribution registration algorithm is an algorithm that applies a three-dimensional point statistical model. It uses standard optimization techniques to determine the optimal match between two point clouds. Since most scan matching algorithms need to find the correspondence between the used features, its calculation time is often long. NDT, on the other hand, because it does not need to use the feature calculation and matching operation of the corresponding point in the matching process, its time calculation efficiency is considerable, and it is suitable for the registration processing of large point cloud data. The specific algorithm process is as follows: 

![avatar]( a05d6315744a4c57b06462cfa114936c.png) 

>  Overall, the registration process of the algorithm is divided into four steps: (1) Compute the normal distribution of the target point cloud by dividing the area covered by the point cloud scan into "voxels" of the same size. Each voxel contains a set of points. The algorithm calculates the mean and covariance matrix of the midpoints of each voxel. (2) Based on the initial transformation, the algorithm aligns the source cloud with the target point cloud. Then, it finds the sum of the statistical likelihood of each alignment point located at the voxels (in the source cloud) around the point according to the normal distribution of the target point cloud. (3) To improve the registration, the algorithm maximizes the probability score of the source cloud on the normal distribution of the target point cloud. This is achieved by iteratively optimizing the angle and translation estimates. (4) Repeat the alignment process between the source point cloud and the target point cloud using the new transformation in the previous step, and then repeat the optimization. When the maximum number of iterations or the accuracy threshold is met, the algorithm stops. This accuracy threshold is a measure of the change in angle and translation estimates from one iteration to another. See the references for more details. 

#  Implementation code 

>  NDT.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574056652
 ```  
#  III. Achieving results 

![avatar]( 10b0214f83f84d2b94d98fc1522f38cd.png) 

>  Note: We should not set the side length of the voxels too small, otherwise each voxel contains too few points will lead to the failure to construct a normal probability density function, so that the initial layer of the function is 0, and the registration process cannot be carried out down. 

#  References 

>  [1]The Normal Distributions Transform: A New Approach to Laser Scan Matching. [2]The Three-Dimensional Normal-Distributions Transform — an Efficient Representation for Registration, Surface Analysis, and Loop Detection. [3]Matlab帮助文档（选择函数名按F1） 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Mean curvature definition: is the average value of two orthogonal curvatures perpendicular to each other at any point on a curved surface in space. If a set of orthogonal curvatures perpendicular to each other can be expressed as K1, K2, then the average curvature is: K = (K1 + K2)/2. Based on this, we will continue the content in the previous blog (Matlab point cloud principal curvature calculation) and calculate the average curvature of the principal curvature of the point cloud. 

#  Implementation code 

>  MeanCurvature.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574039760
 ```  
#  III. Implementation code 

![avatar]( 76fced93f0e848b9970148d2aea5947f.png) 

#  reference 

>  [1] Matlab point cloud principal curvature calculation 



--------------------------------------------------------------------------------

#  I. Introduction 

Note: The Matlab version is 2022b. 

>  The specific calculation process is as follows: 1. Use voxels to downsample the original point cloud. Here we need to set the size of the voxels (optional). 2. Use the ISS algorithm to obtain the key points of the two point clouds. 3. Use the FPFH descriptor to describe the characteristic relationship between each ISS key point and its adjacent points. 4. Build a kdtree based on the FPFH vector of the key points in the target point cloud. In this way, we can use the key points in the source point cloud as query points to obtain the nearest point corresponding to each query point (ie, the ISS key points in the target point cloud). 5. Finally, perform coarse registration on the point cloud based on matching points. 

#  Implementation code 

>  ISS_FPFH.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957403053
 ```  
#  III. Achieving results 

![avatar]( 455faf0c5d1247dd9af0ff113e1fd9b3.png) 

 ![avatar]( 6cf386dfa8f5451997736a6eb202527b.png) 

#  reference 

>  [1] Matlab help document [2] Matlab extracts feature points based on ISS and FPFH 



--------------------------------------------------------------------------------

#  I. Introduction 

The Matlab version is 2022b. 

>  ICP registration and color point cloud registration are both called local registration methods because they both rely on rough alignment for initialization. Algorithms like global registration do not require initialization for alignment, but they usually produce less tightly aligned results and are used as initializers for local methods. FGR is such an algorithm, and the entire algorithm flow is as follows: 

![avatar]( d249ad7d65554b28b10cba7fa4ae9d52.png) 

#  Implementation code 

The relevant parameters of this method can be read in detail in the comments section of the code. 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574099800
 ```  
#  III. Achieving results 

![avatar]( d0bae324b7ad4a059c9e7ab203ed7924.png) 

 ![avatar]( 5222005eb4f5477e966a09c3d7ed727e.png) 

#  reference 

>  [1] Matlab Help Documentation [2] Matlab Fast Global Registration (FGR) 



--------------------------------------------------------------------------------

