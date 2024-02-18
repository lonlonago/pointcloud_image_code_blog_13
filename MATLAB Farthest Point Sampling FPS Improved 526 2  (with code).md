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

