# Literature Review

Approaches or solutions that have been tried before on similar projects.

**Summary of Each Work**:

- **Source 1**: [A Survey of of Machine Learning Methods for Time Series Prediction]

  - **[DOI](https://doi.org/10.3390/app15115957)**
  - **Objective**: Surveying and comparing tree-based machine learning and deep learning models for time series forecasting. 
  - **Methods**: Review of almost 80 studies comparing the two methods
  - **Outcomes**: The paper shows that tree-based machine learning models are usually faster and perfom well on structured data, while deep learning modelss are better at capturing complex temporal patterns. The paper also shows that hybrid models increase accuracy, suggesting to start with tree-based machine learning models first and then considering deep learning models to improve performance. 
  - **Relation to the Project**:
Which are the models commonly used for my problem?
This paper explores different ML methods, showing that Tree-based models and neural networks (RNNs and CNNs) are among the most common ML methods used, with emerging models like Attention-based architectures also gaining more popularity.
Which format must the training data have?
This article shows that according to what model is used, the data has a different format. Still, shared practices can be found, for example, categorical features need to be properly encoded (like we had to do when developing our model). 
How much training data is typically used in similar problems?
This article shows that for a competition regarding sales prediction of Walmart (an american supermarket chain) a dataframe with 42.840 features was given to the competition participants. Of course Walmart is a much bigger entity than the bakery we considered, but it shows how much data can be gathered for predicting sales.  
Are there pretrained models I can use for time series prediction? 
This paper doesn't dig deep into this topic, it just says it is an interesting way to reduce computational costs. 

- **Source 2**: [Unified Training of Universal Time Series Forecasting Transformers]

  - **[Link](https://ink.library.smu.edu.sg/cgi/viewcontent.cgi?article=10906&context=sis_research)**
  - **Objective**: Developing a universal pre-trained transformer model for time series forecasting 
  - **Methods**: Development of MOIRAI: Masked encoder-based universal time series forecasting. 
  - **Outcomes**: Shows that MOIRAI can handle multiple frequencies, different numbers of variables, and provide flexible probabilistic forecasts. MOIRAI performs well compared to specialized models, too.
  - **Relation to the Project**:
Which are the models commonly used for my problem?
This paper looks into many different models for time series predictions like naive forcastings, theta methods, gradient boosting models and wavenets to mention a few. 
Which format must the training data have?
This paper also shows that data can be formatted in a variety of ways. A similarity to our project, is that they used values indexed by time, like we did by inserting a time index "t". 
How much training data is typically used in similar problems?
This paper does not look at a similar problem. 
Are there pretrained models I can use for time series prediction? 
Yes, MOIRAI is a pre-trained model. Still, it benefits from massive and diverse data to be trained on in order for it to be able to make generalizations, which would probably not make it fit to be used in our project. If hundreds of bakeries were being considered, then MOIRAI could be useful. 


- **Source 3**: [Food Industry Sales Prediction. A Big Data Analysis & Sales Forecast of Bake-off Products]

  - **[Link](https://www.diva-portal.org/smash/get/diva2:1563491/FULLTEXT01.pdf)**
  - **Objective**: Identifying the factors that affect sales of bread at Coop Värmaland and to predict future sales in order to reduce food waste and increase profit
  - **Methods**: Big data analysis and exploratory data analysis. Time series forecasting (prophet) and ML models including decision trees, random forest and neural networks. 
  - **Outcomes**: the time series based models performed best. Prophet was number 1, with a MAPE of 8-9%. 
  - **Relation to the Project**:
Which are the models commonly used for my problem?
Many models can be used such as movin average models, autoregressive models, prophet and  recurrent neural networks to name a few mwntioned in this thesis. 
Which format must the training data have?
This thesis structured the data in a very similar way to how we did it, but only had one output variable. 
How much training data is typically used in similar problems?
This thesis has a 80/20 split, with 80% data used for training and 20% for testing. 
Are there pretrained models I can use for time series prediction?
This thesis does not mention pretrained models. 

