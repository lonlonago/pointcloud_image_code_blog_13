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

