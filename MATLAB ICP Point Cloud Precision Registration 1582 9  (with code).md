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

