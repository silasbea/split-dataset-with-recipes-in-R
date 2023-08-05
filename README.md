# split-dataset-with-recipes-in-R

R uses the rsample package in machine learning to split data into training and testing sets and the recipes package to do some feature engineering, handle missing values, vectorization, feature scaling and the preprocessing the data.

In this R Markdown, our Housing dataset has been split into training and testing datasets using rsample. If you don't already have these packages installed, you can of course install with install.packages('rsample') and install.packages('recipes')

```{r}
library(dplyr)
library(tidyr)
library(recipes)

training_data %>%  #data to pipe into the recipe
  recipe() %>%  #start with recipe
   step_normalize(everything()) %>%  #normalize then preprocess
  prep() -> recipe #end with prep

  recipe
```
After running the training data through recipes;

# Recipe

── Inputs 
Number of variables by role
undeclared role: 5

── Training information 
Training data contained 408 data points and no incomplete rows.

── Operations 
• Centering and scaling for: price, area, bedrooms, bathrooms, ... | Trained

# Juice!
Final step is juicing the recipe. Neat huh?
```{r}
library(dplyr)
library(recipes)

juice(recipe) -> juiced
juiced

```
A normalized dataset results. 
Pull the repo and try it out.

Silas Bamidele