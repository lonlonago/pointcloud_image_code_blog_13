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

