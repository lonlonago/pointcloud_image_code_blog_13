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

