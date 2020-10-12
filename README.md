#### Probabilistic Experiment   
##### - Distance from origin after 10 steps in a 1-dimension stocastic walk, with uniform steps between -1 and 1 (Brownian Motion).
This probabilistic experiment will be to simulate a stocastic walk in 1-dimensions, (hopefully expanded to m-dimensions), and calculating the probability of being x distance from the origin.    

In our Experiment, with a 1-dimension space, the walk starts at 0, and with every step, has a uniform probability of moving between -1 and 1 from the current position.    
This random variable in this experiment will be uniformly distributed between -1 and 1 (but with options for different step distributions).  

After 100000 steps what is the expected value and variance of the stocastic process?  

This could be useful for physics, stock market modelling etc.  

#### Calculating the Expected Value and the Standard Deviation for 1-dimensional steps:

###### Individual step:
Every step have a uniform probability between -1 and 1.
Uniform Distribution equations can be found here: https://en.wikipedia.org/wiki/Continuous_uniform_distribution.

Step Expected Value: (1/2).(a+b) -> (1/2)((-1)+1) = 0 

Step Variance: (1/12).(b-a)^2 -> (1/12).(1-(-1))^2 = 4/12 = 1/3  
Step Standard Deviation: Variance^(1/2) -> (1/3)^(1/2)  
Distribution: Uniform

###### Brownian Motion:
Calculating the Expected and Standard Deviation with Uniform steps.  
Every step is independant of the previous steps.

Brownian Motion Expected Value: Expected(after n steps) = Expected(step 1) + Expected(step 2) ... + Expected(step n) = 0 + 0 + ... + 0 = 0

Brownian Motion Variance: Variance(after n steps) = Variance(step 1) + Variance(step 2) +...+ Variance(step n) = (1/3) + (1/3) +...+ (1/3) = (n/3)   
Brownian Motion Standard Deviation: Variance^(1/2) -> (n/3)^(1/2)  
Distribution: Normal

###### Distance from Origin:
Calculating the Expected and Standard Deviation of the Distance from the Origin after n-steps in a 1-dimensional space.  
We are getting the distance of a 1-dimensional space ranging from -n to n, this is equivalent (for our distance formula) to getting the absolute value of the final locations of the Brownian Motion.  
Since the Brownian Motion is Normal Distributed, this creates a Half-Normal Distribution.  
Half-Normal Distribution equations can be found here: https://en.wikipedia.org/wiki/Half-normal_distribution.  

Distance Expected Value: Expected(after n steps) = (Variance(Brownian Motion).(2))^(1/2) /(pi)^(1/2) = (n/3).((2)^(1/2) /(pi)^(1/2))  

Distance Variance: Variance(after n steps) = Variance(Brownian Motion)x(1 - (2/pi)) = (n/3).(1 - (2/pi))  
Distance Standard Deviation: Variance^(1/2) -> ((n/3).(1 - (2/pi)))^(1/2)  
Distribution: Half Normal  

### For n = 10:

##### Expected: (n/3)x((2)^(1/2)  /(pi)^(1/2))= 2.6596152026762185
#####  Standard Deviation: (n/3)x(1 - (2/pi))^(1/2) = 1.100575951691384
##### Distribution: Half Normal Distribution (https://en.wikipedia.org/wiki/Half-normal_distribution)  

The model agrees with these results.  
  
#### Potential Improvements:
Run on n-dimensions 
* Need a way to calculate the expected Expected and Standard Deviations in n-dimensions  
* Need a different distance function for dimensions > 1 ("Manhattan distance", or "Absolute-value")?
