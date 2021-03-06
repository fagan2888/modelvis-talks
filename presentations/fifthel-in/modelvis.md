theme: Olive Green, 9

# [fit] **Model Visualisation**
## ___
## Amit Kapoor
## @amitkaps

---

# **Story**
## ___
## “We don’t see things as they are, we see them as we are.”
### *— Anais Nin*

---

# **The Blind Men & the Elephant**
## ___


---

# **The Blind Men & the Elephant**
## ___
### “And so these men of Indostan
### Disputed loud and long,
### Each in his own opinion
### Exceeding stiff and strong,
### Though each was partly in the right,
### And all were in the wrong.”
#### — *John Godfrey Saxe*

---

# **The Elephant: Data**
## ___
## “Data is just a clue to the end truth”
### *— Josh Smith*

---

# **The Men: Building Models**
## ___
## "All models are wrong, but some are useful"
### *— George Box*

---

# **Layers of Abstraction**
## ___
## **Data** Abstraction
## **Visual** Abstraction
## **Model** Abstraction

---

# **Machine Learning (ML) Speak**
## ___
## **Data** Transformation
## **Visual** Exploration
## **Model** Building

---

# **ML Pipeline**
## ___

### Data Transformation  — — — —  Model Building
###    *(Tidy Data)*                                 
###         │                                 
###         │                                 
###         │                                 
### Visual Exploration   
###    *(Data-Vis)*       

---

# **ML Pipeline++**
## ___

### Data Transformation  — — — —  Model Building
###    *(Tidy Data)*                 **_(Tidy Model)_**      
###         │                           │     
###         │                           │     
###         │                           │     
### Visual Exploration           **Model Exploration**
###    *(Data-Vis)*                   **_(Model-Vis)_**

---

# **Model Exploration**
## ___
## Use visualisation to aid the transition of **implicit knowledge** in the data and your head to **explicit knowledge** in the model.

---

# **Model Visualisation**
## ___
## **Model-Vis** approach
## **Tidy Model** concept

---

# **Example: Buying a Car**
## ___
## Colloquially: **“kitna deti hain”**

---

# **Example: Buying a Car**
## ___
## Colloquially: **“kitna deti hain”**
##    
## Translates to *“What is the mileage, for the price I pay?”*

---

# **Cars Dataset**
## ___
## Scraped from **comparison** website
## Refined & **tidied** up
## **Base version** for **petrol** cars
## Price **< ₹ 1,000K**
## n = **42**


---

**brand**    **model**    **price**    **kmpl** 
Tata     Nano       199    23.9	   
Suzuki   Alto800    248    22.7	   
Hyundai  EON        302    21.1	   
Nissan   Datsun     312    20.6	   
...      ...        ...    ...

Suzuki   Ciaz       725	   20.7	   
Skoda    Rapid      756	   15.0	  
Hyundai  Verna      774	   17.4	  
VW       Vento      785	   16.1	  

---

![fit](figures/fig_cars_01.png)

---

# **Model-Vis Approach**
## ___
## **[0]** Visualise the **data space**
##   

---

# **Build a Simple Model**
## ___
## Regression: $$price = \beta_0 + \beta_1 * kmpl$$
## **Ordinary Least Square (OLS)**


---

![fit](figures/fig_cars_02.png)

---

# **Model-Vis Approach**
## ___
## **[1]** Visualise the **predictions** in the **data space**

---

# **Change Model Parameters?**
## ___
## Regression: $$price = \beta_0 + \beta_1 * kmpl$$
## Ordinary Least Square
## **// _One-Shot ML Algorithm_ //**

---

# **Modify the Cost Function**
## ___
## Regression: $$price = \beta_0 + \beta_1 * kmpl$$
## ~~Ordinary Least Square~~ 
## **Ridge: L2 Regularisation**

---

![fit](figures/fig_cars_03.png)

---

# **Model-Vis Approach**
## ___
## **[2]** Visualise with **different model parameters**


---

# **Select Model Parameters?**
## ___
## Need more data for the model:
# **Bootstrap**


---

![fit](figures/fig_cars_04.png)

---

![fit](figures/fig_cars_05.png)


---

# **Model-Vis Approach**
## ___
## **[3]** Visualise with **different input datasets**

---

# **Add More Models**
## ___
## Ordinary Least Square (OLS)
## Ridge Regression (alpha = 0.1)
## **Polynomial (n=3)**
## **LOWESS**

---

![fit](figures/fig_cars_06.png)

---

# **Show the Model Space**
## ___
## Ordinary Least Square (OLS)
## Ridge Regression (alpha = 0.1)
## Polynomial (n=3)
## LOWESS
## **ENSEMBLE (Averaging)**

---

![fit](figures/fig_cars_06b.png)

---

# **Model-Vis Approach**
## ___
## **[4]** Visualise the **model space**

---

# **Add More Features?**
## ___
## Search for a better explanation between **price** and **kmpl**
##    
## **type**: **hatchback**, **sedan** 

---

**brand**    **model**    **price**    **kmpl**    **type**
Tata     Nano       199    23.9	   Hatchback
Suzuki   Alto800    248    22.7	   Hatchback
Hyundai  EON        302    21.1	   Hatchback
Nissan   Datsun     312    20.6	   Hatchback
...      ...        ...    ...     ...   

Suzuki   Ciaz       725	   20.7	   Sedan
Skoda    Rapid      756	   15.0	   Sedan
Hyundai  Verna      774	   17.4	   Sedan
VW       Vento      785	   16.1	   Sedan

---

![fit](figures/fig_cars_07.png)

---

# **Add Features to One Model**
## ___
## OLS Regression
## $$price = \beta_0 + \beta_1 * kmpl + \beta_2 * type $$

---

![fit](figures/fig_cars_08a.png)

---

# **Build Two Models**
## ___
## type = **hatchback**: $$price_h = lowess(kmpl_h)$$
## type = **sedan**: $$price_s = lowess(kmpl_s)$$


---

![fit](figures/fig_cars_08b.png)

---

# **Model-Vis Approach**
## ___
## **[5]** Visualise the **many models together**

---

# **Keep Adding Feature**
## ___
## Can get complex really fast!
##    
## Add one more feature: **bhp**

---

**brand**    **model**    **price**    **kmpl**    **type**        **bhp**
Tata     Nano       199    23.9	   Hatchback    38
Suzuki   Alto800    248    22.7	   Hatchback    47
Hyundai  EON        302    21.1	   Hatchback    55
Nissan   Datsun     312    20.6	   Hatchback    67
...      ...        ...    ...     ...         ...

Suzuki   Ciaz       725	   20.7	   Sedan        91
Skoda    Rapid      756	   15.0	   Sedan       104
Hyundai  Verna      774	   17.4	   Sedan       106
VW       Vento      785	   16.1	   Sedan       104

---

![fit](figures/fig_cars_09.png)

---

# **Build a New Model**
## ___
## OLS Regression
## $$price = \beta_0 + \beta_1 * kmpl + \beta_2 * type + \beta_3 * bhp$$ 

---

![fit](figures/fig_cars_10.png)

---

# **Visualise Model Errors**
## ___
## Visualise $$\epsilon = price_{pred} - price$$

---

![fit](figures/fig_cars_11.png)


---

![fit](figures/fig_cars_12.png)

---

# **Errors Easier to Visualise**
## ___
## Move away from features
## Address curse of dimensionality

---

# **Prediction vs. Error**
## ___
## Test Robustness of the Model
## Do Cross Validation - 6 fold

---

![fit](figures/fig_cars_13.png)

---

# **Build the final Model**
## ___
## OLS Regression
## $$price = \beta_0 + \beta_1 * kmpl + \beta_2 * type + \beta_3 * bhp$$ 
## Cross Validation - 6 fold

---

![fit](figures/fig_cars_14.png)


---

# **Model-Vis Approach**
## ___
## **[6]** Visualise the errors in **model fitting**

---

# **Model-Vis Approach**
## ___
### **[0]** Visualise the **data space**
### **[1]** Visualise the **predictions** in the data space
### **[2]** Visualise with **different model parameters**
### **[3]** Visualise with **different input datasets**
### **[4]** Visualise the **entire model space**
### **[5]** Visualise the **many models together**
### **[6]** Visualise the **errors** in **model fitting**

---

# **Model-Vis & ML Approach**
## ___
### **[0]** **DATA VIS**: the data space
### **[1]** **PREDICTION**: the predictions in the data space
### **[2]** **TUNING**: with different model parameters
### **[3]** **BOOTSTRAP**: with different input datasets
### **[4]** **ENSEMBLE**: the entire model space
### **[5]** **N-MODELS**: the many models together
### **[6]** **VALIDATION**: the errors in model fitting

--- 

# **Model Explosion**
## ___
### **Base Models = 7**
#### OLS Regression (p = 1, p = 2, p = 3)
#### Ridge Regression, Polynomial, LOWESS (total, by type)
### + **Add Tuning Models**
### + **Add Bootstrap Models**
### + **Add Ensemble Models**
### + **Add Cross-Validation Models**

---

# **Challenge with Model**
## ___
## Keep track of **prediction** & **errors**
## Keep track of **model output parameters**

---

# **Tidy Model**
## ___
## Augment **predictions** & **errors** to dataset
## Create **output parameters** data frame
## Visualise like **Tidy Data**

---

# **Tooling**
## ___
## Started with python and challenging
## **broom** package in R (by David Robinson)

---

```{r}
library(dplyr)
library(broom)
set.seed(2014)

# Move Bootstrap Output to Tidy Model
bootcars <- cars %>% 
            bootstrap(100) %>%
            do(augment(smooth.spline(.$kmpl, .$price, df=4), .))

# Plot the Output           
ggplot(bootcars, aes(kmpl, price)) + geom_point() +
    geom_line(aes(y=.fitted, group=replicate), alpha=.2)

```

---

# **Model-Vis**
## ___
## Similar challenges **to Data-Vis**
## More an **Art**, than a Science
## Essential in **ML Model Pipeline**
## Both **to Explain** or **to Predict**
## Scope for **easier tooling**

---

# **Model-Vis**
## ___
### Cars Dataset (n = 833, p = 63)
### [https://github.com/amitkaps/cars](https://github.com/amitkaps/cars)
###    
### Talk Code
### [https://github.com/amitkaps/modelvis](https://github.com/amitkaps/modelvis)

---

# [fit] **Model Visualisation**
## ___
## Amit Kapoor
## @amitkaps
##    
## [amitkaps.com](http://amitkaps.com)
