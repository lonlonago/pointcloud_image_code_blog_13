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

