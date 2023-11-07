# Advanced-Statistics

1. A probability density function (PDF) is a statistical measure that calculates the likelihood that a random variable will fall within a certain range of values

2. There are different types of probability distribution function

 Binomial ditribution
 Possion distribution
 Gaussin distribution
 Normal distribution

3. from scipy.stats import norm 
import numpy as np 

data_start = -8

data_end = 16

data_points = 8

data = np.linspace(data_start, data_end, data_points) 

mean = np.mean(data) 

std = np.std(data) 

probability_pdf = norm.pdf(4 , loc=mean , scale=std)
print(probability_pdf)


4. The Properties of binomial distribution are:
    
      1. There are fixed possible trails
      2. There are only two posssible outcomes
      3. The probability of success remains constant for each trial

5. from scipy.stats import binom 
 
n = 4
p = 0.4

r_values = list(range(n + 1)) 

mean, var = binom.stats(n, p) 

dist = [binom.pmf(r, n, p) for r in r_values ] 

print("r\tp(r)") 

for i in range(n + 1): 
	
    print(str(r_values[i]) + "\t" + str(dist[i])) 

    print("mean = "+str(mean)) 

    print("variance = "+str(var))


6. import numpy as np 
import matplotlib.pyplot as plt 
import pandas as pd 
%matplotlib inline 

N = 400

data = np.random.randn(N) 

count, bins_count = np.histogram(data, bins=10) 

pdf = count / sum(count) 

cdf = np.cumsum(pdf) 

plt.plot(bins_count[1:], pdf, color="black", label="PDF") 

plt.plot(bins_count[1:], cdf, label="CDF") 

plt.legend()


7. Binomila distribution - Binomial distribution is the one in which the number of outcomes are only two, that is success or failure

Poisson dsitribution - Poisson distribution: Poisson distribution is the one in which the number of possible outcomes has no limits

8. import numpy as np
import matplotlib.pyplot as plt

s = np.random.poisson(10, 1000)

count, bins, ignored = plt.hist(s, 10, density=True)

plt.show()


9.The mean of the binomial distribution is always equal to p, and the variance is always equal to pq/N

10. This means that most of the observed data is clustered near the mean, while the data become less frequent when farther away from the mean
