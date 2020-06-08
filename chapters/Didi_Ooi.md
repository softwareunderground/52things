# Simple Machine Learning: A Mini Tutorial  

Coming from a pure geology background in the undergraduate, without any statistics prerequisites – you can imagine the horror of jumping into a PhD that deals with a horde of data under geology supervisors! Here I would like to present to take us through the whole basic machine learning workflow, which includes the underrated exploratory data analysis (EDA). This is something I wished I had when I started my PhD and life I imagine, would be simpler. The goal for this multivariate analysis is to look for the highest independence between variables that correlate to produce the best predictor model.  

## 6 Steps in a Machine Learning workflow

**1.	Understand each variable independently**  
    This first step, often overlooked by many, is crucial as it will significantly affect our machine learning model. We can simply do univariate analyses by knowing the distribution shape of our data, the range of values (including outliers), determine the normality, quantify the missing-ness (N/A, nulls) and perform descriptive statistics on them.
Statistical Plots: *Box plot, Quantile-quantile (QQ) plot*  

**2.	Feature engineering**  
    The portion of Machine Learning that validates the need for us human geoscientist – the subject matter expertise (SME)! Our job here is to determine whether a set of variables should be converted to categorical (low-medium-high), to make new metrics (Variable 1/Variable 2), transform the data (log or square root), create formulaic columns, manually categorize data (with tags), handle data imputation, and/or deal with outliers.
Tools: *Pandas, Excel (yes for small data!)*   

**3.	Understand bivariate relationship**  
    Linear regression on data relationships are commonly used by geoscienstists, but the statistical significance of the regression (*p-value*) and the statistically significant differences (*ANOVA* or *Kruskal Wallis, Chi-square*) are too often neglected. *R<sup>2</sup>* only tells us the potential dependency among predictors, but it is not a validation of whether they are and statistically significant. *P-value* helps to quantify our ‘guessing’. The simple trick here is for the bivariate data to have the smallest *p-value* and highest *R<sup>2</sup>*.
Tools: *Scikit-learn, Plotly, SciPy*  

**4.	Exploit multivariate patterns**   
    To understand variation of our dataset, aka relationship of ALL variables versus ALL variables, we can use dimensionality reduction techniques such as *Principal Component Analysis*. This is important especially if we have more than 10 interdependent variables! We can get sense of the multi co-linearity of your variables and identify variables (and which of them are outliers) that provide the most information. Here we can get rid of uninformative variables for your model creation, unless you are looking to determine an outlier like a fault, salt bodies, or a lost circulation zone?
Tools: *prcomp in R, scikit-learn*  

**5.	Train your Machine Learning model**
Now we are ready to create your first multivariate model! Divide up your data into a training and validation set, preferably in 80:20. Lower ratio allows for better predictability, but only do this if you have really large data. Start with the minimum number of variables and train competing models with a simple algorithm, like *random forest*.
Tools for 5-6: *TensorFlow, Scikit-learn, Keras, Caffe, PyTorch etc*  

**6.	Prediction!**
Now use your remaining 20% of your dataset set aside for validation to test your model. The model performances typically entails: *residual standard error (RSE), root mean square error (RMSE), degrees of freedom, adjusted R2, F-stats* and *p-value*. *Residual* analysis tells us the difference between actual data against the value predicted by your model. This is the part where you will have to repeat step 2 and 3 – 6 to get the ‘best model’, or immediately apply model(s) to new unseen data. Run sensitivity analysis on parameters and compare outputs of competing models!

Voila! You are now ready for the next adventure in being an AI geoscientist! 
