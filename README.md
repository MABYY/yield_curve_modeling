# Yield curve modeling

#### Overview
Interest rate term structure modeling is of fundamental importance both to financial market players and to monetary policy makers. Broadly, yield curve modeling can be classified in two categories: those models that do not impose no-arbitrage restrictions and those that do. These approaches differ in their construction. In the former group, the factor loadings depend only on a decay parameter usually called “exponential decay parameter”. In the latter group, the factor loadings result from imposing no-arbitrage restrictions across bonds of different maturities. However, both groups of model assume that the yields can be expressed as affine equations of a reduced number of unobserved factors. Their variability completely explains that of the yields. 
Recent studies incorporate macro-economic variables, such as inflation and economic activity, as explanatory variables in the models. However, they do not depart substantially from the original settings. 

## The Model

The three factor Nelson Siegel interpolation (Nelson and Siegel 1987) became popular due to its goodness of fit and parsimony. The original NS model is static and built for fitting the cross section of yields, but not for out of sample forecasts.The authors obtain the function of the yield curve by integrating the forward rates. The resulting function for maturity n is:

<img width="364" alt="image" src="https://github.com/user-attachments/assets/5d0edc91-b1d0-44a6-a36b-3838510df62e" />

For any value of λ, it is possible to calculate sample values of the two regressors. Then, the best fitting values of the two regressors can be calculated by using linear least squares. By repeating this procedure over a grid of values for λ, the best fitting values of L, S, C and λ are obtained.

The dynamic version of the Nelson and Siegel interpolation (DNS) was developed by Diebold and Li (2006). The three latent factors 𝑋𝑡 = [𝐿𝑡, 𝑆𝑡, 𝐶𝑡] are labeled as Level, Slope and Curvature respectively. To estimate the parameters 𝑋𝑡 the authors follow Nelson and Siegel (1987). They fix at 𝜆𝑡 = 0,0609, which maximizes the loading on the medium-term factor at exactly 30 months, and compute the values of the two regressors and the corresponding panel of residuals. Then, they apply ordinary least squares to estimate factors. 

Diebold, Rudebusch and Borag Aruoba (2006) elaborated an extension to the DNS model as an attempt to characterize the dynamic interactions between the macroeconomy and the yield curve. They find strong evidence of the effects of macro variables on future movements in the yield curve and for a reverse influence as well.The model carries the three latent factors above mentioned, but now includes observable macroeconomic variables. Once again, 𝑋𝑡, is modeled as a VAR(1) process and is extracted by using the Kalman Filter.

<img width="350" alt="image" src="https://github.com/user-attachments/assets/d7290b07-4723-4366-966f-b9aa3c9cd8bc" />
<img width="512" alt="image" src="https://github.com/user-attachments/assets/5eca42c1-5bf2-4372-8d93-b88f8caf4ebd" />

Litterman and Scheinkman (1991) showed that a three factor PCA model of the term structure fits the data in a remarkable way and is useful for hedging. Following these attemps, BOFA's approach consists of a two-step process. Firt, they model each interest rate using PCA, which explains more than 95% of total variability. Then, they model the first two PCA factors of each yield with global and macro variables. 



