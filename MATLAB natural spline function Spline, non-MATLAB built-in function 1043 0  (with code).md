#  I. Introduction 

>  Purely out of curiosity, I found a book to learn about the implementation of spline functions, as follows: 

Derivation process: 

![avatar]( 52765418b94946d5baa8cdd046a95801.png) 

 ![avatar]( 5dd9bc0374004414906c0b595d58f7ff.png) 

 ![avatar]( b85aca8d17904e4492252e165841071d.png) 

 Algorithm flow: 

![avatar]( d00c4510f955477f8e80c81321f01e0e.png) 

 ![avatar]( 7013d70e899f43f983ec6cde71919678.png) 

>  In the above 

          l 

          、 

          u 

         l、u 

     L and u are the upper and lower triangular matrices of the coefficient matrix, respectively, and the algorithm flow here only constrains the second derivative of the two ends to 0, without adding more constraints. For more details, please refer to the references at the end of the article. 

#  Implementation code 

>  splinefunc.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574097890
 ```  
#  III. Achieving results 

![avatar]( 2030fedbc158437089caaa34f789ed59.png) 

>  From the perspective of the implementation, the derivation of the formula and the algorithm flow are completely ok. 

#  References 

>  [1]《Numerical Analysis-Burden Faires 9th》 

