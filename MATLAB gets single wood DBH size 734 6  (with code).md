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

