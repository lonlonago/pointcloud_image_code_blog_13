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

