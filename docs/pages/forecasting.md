---
layout: default
---

[Introduction](./../index.html) | [Correlation Analysis](./../pages/corr_analysis.html) | [Forecasting](./../pages/forecasting.html) | [Conclusion](./../pages/conclusion.html)

In this section model the relationship between energy consumption and weather parameters where we hypothesise that weather has an impact on energy consumption in this particular location. Additionally, if weather does indeed affect energy consumption can a model be created to predit the same?

## Regression models
To setup the regression model, we first check the correlations between the regressors, as high correlation between them would lead to unstable parameters.

| -  |   T  |   P   |   U  |   Ff |   Td |
|:---|:-----|:------|:-----|------|:-----|
| T	 | 1,0	|     	|      |      |	     |
| P	 | 0,1	|  1,0	|      |     	|      |
| U	 | -0,7	| -0,2	| 1,0	 |    	|      |
| Ff | 0,1	| -0,3	| -0,2 |	1,0	|      |
| Td | 0,7	|  0,0	| 0,0	 | -0,1	|  1,0 |

Following the correlations listed in the table above it is evident that Temperature(T) has a high correlation with the Dew point temparature(Td) and humidity, Td however has a low correlation to U. It is therefore imperative that one the two measures of temperature be ommitted from the model.

### Regression Results

#### Industry Consumer

|    coef            |   std err    |    t     | P\>\|t\| | \[0.025   0.975\]  |
|:-------------------|:-------------|:---------|:-------- |:-------------------|
|P\:          1.6605 |    0.081     | 20.377   |  0.000   |  1.501      1.820  |
|U\:          3.1617 |    0.708     | 4.464    |  0.000   |  1.773      4.550  |
|Ff\:        13.4256 |    8.082     | 1.661    |  0.097   | -2.417     29.268  |
|Td\:       -10.3302 |    2.385     | -4.331   |  0.000   | -15.006     -5.655 |

|   R-Squared  | Adj. R-squared |  Durbin-Watson |  Jarque-Bera   |   Skew   | Kurtosis | No. Observation |
|:-------------|:---------------|:---------------|:---------------|:---------|:-------- |:-------|                                    
|   0.576      |    0.576       |    0.225       |  981.370       |   0.383  |   1.546  |  8717  |

This results indicate that the selected weather parameters are significant in explaining energy consumption in the industrial setting. However, in the overall the model has a relatively weak predicting power as seen from an R-squared 57.6% and high statistical value to the Jarque-Bera statistics. While these weather parameters can explain some of the variance in consumption a reasonable amount of variance is not accounted for by the model.

#### Commercial Building

|    coef            |   std err    |    t     | P\>\|t\| | 
|:-------------------|:-------------|:---------|:-------- |
|P\:          0.7326 |    0.010     | 74.17    |  0.000   |  
|U\:         -2.6653 |    0.086     | -31.05   |  0.000   |  
|Ff\:        25.4088 |    0.980     | 25.936   |  0.000   |
|Td\:         0.5557 |    0.289     | 1.922    |  0.055   |

|   R-Squared  | Adj. R-squared |  Durbin-Watson |  Jarque-Bera   |   Skew   | Kurtosis | No. Observation |
|:-------------|:---------------|:---------------|:---------------|:---------|:-------- |:-------|                                    
|   0.910      |    0.910       |     0.122      |   401.609      |    0.301 |    2.138 |  8724  |

Regressing weather data on electricity consumption on a building indicates that weather does drive consumption based on the highly significant parameters obtained from the regression. Weather appears to account for a signifiance amount of variance on the consumptions. Additionally a weather parameter such as temperature (Td) has a positive relationship with electricity consumption while humidity has a negative effect when all other parameters are held constant. 
Despite weather being a significant driver of energy consumption in a commercial building, it is worth noting that the residuals from this model still indicate non-normality features; skew (0.301) and kurtosis (2.138).

#### Apartment Block


|    coef            |   std err    |    t     | P\>\|t\| | 
|:-------------------|:-------------|:---------|:-------- |
|P\:           0.782 |    0.017     | 46.806   |  0.000   |  
|U\:         -5.4652 |    0.145     |-37.637   |  0.000   |  
|Ff\:        23.9900 |    1.658     | 14.473   |  0.000   | 
|Td\:         5.4926 |    0.489     | 11.230   |  0.000   |

|   R-Squared  | Adj. R-squared |  Durbin-Watson |  Jarque-Bera   |   Skew   | Kurtosis | No. Observation |
|:-------------|:---------------|:---------------|:---------------|:---------|:-------- |:-------|                                    
|   0.696      |    0.198       |    0.198       |  1045.021      |   0.813  |   3.480  |  8728  |

Similar to a commercial building, weather parameters are highly significant when regressed on consumption in an apartment block. An increase in humidity leads to reduction in electricity consumption, all other weather parameters indicate a positive linear relationship where a unit increase in the parameter leads to an increase in the consumption of electricity.





[back](./../pages/forecasting.html)
