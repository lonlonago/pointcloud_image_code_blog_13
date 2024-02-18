#  Overview of the principle 

>  The basic principle of the inflection point method of adaptive k value can be described as follows: as the number of target clusters increases, the number of samples in the target cluster set gradually decreases, and the distance between the samples and the center of the cluster is closer, the J value of the objective function also becomes smaller. When the number of target clusters is greater than the optimal number of classes k, the subset of clusters is formed by merging multiple clusters into a single cluster split. At this time, the objective function J suddenly becomes smaller and keeps slowing down. Therefore, by setting different target class numbers to calculate the objective function J value and plotting the cluster number-objective function curve, the k value corresponding to the inflection point (mutation point) of the objective function curve is the optimal number of target cluster classes. 

#  Implementation code 

>  InflectionPointMethod.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574085991
 ```  
#  III. Achieving results 

![avatar]( 1485fdc98d6742929f7121638ba13d37.png) 

>  According to the ideas in the paper to test the method, the test effect is not very ideal, because the original data source is roughly 8 categories, but the best k value detected by this method should be 5 categories, and further research is needed later. 

#  References 

>  [1] Research on key technologies for inspection of airborne laser point cloud transmission lines 

