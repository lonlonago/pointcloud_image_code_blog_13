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

