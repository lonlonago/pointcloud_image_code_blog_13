#  I. Introduction 

##  1.1 Fitting plane by least squares method 

>  Previously, we used the most classic method to fit the plane in least squares (point cloud least squares method to fit the plane). The derivation process is as follows: 

![avatar]( 7318bf2cd65545e687e6815cd134bd55.png) 

 ![avatar]( 44cf5e00075948a8b4f3b1c5a402b54f.png) 

 ![avatar]( 25ec4278e2764a83929073e54c27969c.png) 

 A closer look reveals that 

          Q 

         Q 

     Q is actually the covariance matrix of the coordinates, and it can be found by inverting it 

          X 

         X 

     X solution. 

##  1.2 SVD angle 

>  However, if we change our perspective, we can obtain another solution. We all know that the eigenvalues of a matrix have this property: 

>  If all the above coordinates are decentrified, i.e. 

          ( 

           x 

           i 

          , 

           y 

           i 

          , 

           z 

           i 

          ) 

          − 

          ( 

           x 

           ^ 

          , 

           y 

           ^ 

          , 

           z 

           ^ 

          ) 

         (x_i,y_i,z_i)-(\hat x,\hat y,\hat z) 

     (Xi, yi, zi) − (x ^, y ^, z ^), then (4) can be changed to: 

>  At this point, let's take a look at this form again. 

           Q 

           ′ 

          X 

         Q'X 

     Q ′ X is actually the residual from the point to the plane, if it is equal to 0, then the 

          X 

         X 

     X is the optimal solution, but we all know that often problems with noise points cannot make the residuals 0, so our actual goal is actually: 

>  Thinking about the above properties, we come to the conclusion that: 

>  that is 

           Q 

           ′ 

         Q' 

     Q ′ matrix 

           i 

            m 

            i 

            n 

         \lambda_{min} 

     When λ min, the corresponding eigenvector is the optimal solution we want 

          X 

         X 

     X, so we can use the SVD algorithm to solve for 

          X 

         X 

     X solution ( 

          a 

          , 

          b 

          , 

          c 

         a,b,c 

     A, b, c coefficients), and we decentrified before, so we can get it from the centroid point 

          d 

         d 

     d。 

Note: This is just for ease of understanding, intuitive analysis from the perspective of SVD, and more rigorous forms require private mathematical derivation. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574068313
 ```  
>  DrawPlane.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574068313
 ```  
#  III. Achieving results 

![avatar]( cc8a27fbc1244d96bb489036e4eae6b2.png) 

 ![avatar]( 0f7d234c9fa34a0e9393d59e5bfb51e5.png) 

#  reference 

>  [1] Point cloud least squares fitting plane 

