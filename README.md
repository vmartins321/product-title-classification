## Model 
* __Model name__: pcc1
* __Model version__: 3
* __Model training script__: product_categorization/development/v3/experiments/pcc1_v3_sgd.ipynb
* __About__: ~70% of products in the catalog don't have any category data. Additionally, different stores use different catergories that overlap e.g. Clothing vs Clothing & Accessories. A list of mututally exclusive categories for all products was developed based on exploration of the product catalog. The model is trained on products with these categories. This model can be used to predict a category for all products to produce a unified category classification.
* __Use cases__: The predicted categories can be exposed to the user via a product browsing tree in the UI. This is for high level categories only e.g. Clothing, Electronics. This model scored with greater than 90% accuracy across products from major stores. 

## Training
* __Last trained on__: 2017-02-05
* __Training data script__: experiments/training_data_scripts/pcc1_v3_training_data_2018_02_01.ipynb
* __Training data__: 
* project_id = 'my_project'
* gs://data-science/product_categorizer/training/pcc1/v3/2018_02_06/data_labeled.csv
* gs://data-science/product_categorizer/training/pcc1/v3/2018_02_06/pcc1_v3_data_2018_02_01.pkl

## Experiments
* __Ngrams__ word bigrams improved results, whereas character ngrams did not
* __Descriptions__ adding product descriptions had no effect
* __Feature Selection__ feature selection had no effect, including an ensemble model
* __Subsampling__ sampling from each category_2 did not improve results
* __Categories__ masking some percentage of category metadata led to better results than removing all or including all categories

## Results
* __F1_Score__
	* SGD: 0.92
	* MultiNomial Naive Bayes: 0.91
	* Bernoulli Naive Bayes: 0.90
	* LinearSVC: 0.89
	* Random Forest: 0.81
	* LinearSVC + RandomForest: 0.82
