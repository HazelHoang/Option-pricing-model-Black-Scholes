# Option-pricing-model-Black-Scholes
Call, Put, European style options
from math import *
from scipy.stats import norm

#first define these 2 functions
def d1(S,X,T,r,sigma):
    return (log(S/X)+(r+sigma*sigma/2.)*T)/(sigma*sqrt(T))

def d2(S,X,T,r,sigma):
    return d1(S,X,T,r,sigma)-sigma*sqrt(T)

#define the call option price function
def bs_call(S,X,T,r,sigma):
     return S*norm.cdf(d1(S,X,T,r,sigma))-X*exp(-r*T)*norm.cdf(d2(S,X,T,r,sigma))
    
