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

