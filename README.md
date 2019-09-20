# recommender-system-based-on-negative-reviews
Recommender System based on negative reviews:
Nowadays, one of the most important and essential tools in online shopping sites are product recommenders. These recommender systems help users observe and notice more products and purchase them if they wish.
These systems have been implemented in a variety of ways.

The method used in this experiment is different from previous works, which recommends  products to users  based on the their negative comments about a particular product. The advantage of this recommender is that  with respect to the user's negative review,  the negative aspect of the product is identified and then products of the same category are recommended to the user without the mentioned negative aspects. This recommender  system is especially useful when customers want to exchange a product or are looking for a product that does not contain a special feature.

This system works based on amazon products dataset.

Requirements:

Python 3.7

Tensorflow

Keras

Numpy

Scikit_learn

Logging

Pytorch >= 0.4.0

You can see the dataset format in following link:

http://jmcauley.ucsd.edu/data/amazon/ 

first you need to  download the review data and meta data of “ Cell Phones and Accessories” category.

We use product IDs to identify product.

Two ready modules are used in this project. One of them is “Aspect extractor” and the other one is “aspect based sentiment analysis”. 

These modules are already implemented and we change them a little bit in order to use them for predicting.

I forked them in Github changed them a little bit. Here are the links:

https://github.com/asarvi/ABSA-PyTorch

https://github.com/asarvi/aspect-extraction-1

first you should clone the aspect-extraction-master from the following link:

https://github.com/asarvi/aspect-extraction-1

extract  and put amazon dataset in a folder in the main folder of aspect-extraction-master named ‘amazonData’.

to make this work you should download the Glove embeddings dataset from following link and unzip it in data folder:

http://nlp.stanford.edu/data/glove.840B.300d.zip

Now you need to train the “aspect-extraction” and make it work. Run these python files one by one:

-	build_data.py

-	train.py

-	evaluate.py

(if you get errors it is probably for file names or your python version)

Now we should place the “Aspect Based Sentiment Analysis” module in project and make it work:

Clone the module from following link and unzip it in main file of project ( aspect-extraction-master) and rename it to ABSA.

https://github.com/asarvi/ABSA-PyTorch

now we should train this module.

Download and extract the Glove pre-trained word vectors in ABSA folder from the following link:

http://nlp.stanford.edu/data/wordvecs/glove.42B.300d.zip 

run the train.py

to see how it works refer to example.py (you should probably rename your trained model name in line 76  based on .log files created after training in  ABSA  )

(for more information refer to read.me file of this repository)

Now you can run the recommender project!

Run the recommender.py in project main file.

The input is a “product ID “ (you can search in amazon dataset for “asin” each asin is a product ID and you can see it’s features and reviews by searching in those files)

Then you should write  a review ( with a negative aspect necessarily ) and wait for the system to return a bunch of product IDs which are the recommended products for you based on your negative review! 

Example:

Input :

6789300899

The price is too high!

Output:

[‘B004WLX34S’ , ‘B00D4B4MY2’ ,,,,]


## testset and system evaluation

to see the testset data refer to following link:

https://github.com/asarvi/recommender_evaluation

place the testData and evaluator.py in main file of project and run the evaluator.py

the results are in a text file named final_result.txt

 here is the accuracy result of system for 56 samples.(the test set made by expert)



precision	recall	F1_measure

0.14	1	0.25

0.16	1	0.28

0.25	0.5	0.33

0.25	1	0.4

0.25	1	0.4

0.33	1	0.5

0.33	1	0.5

0.33	1	0.5

0.37	0.75	0.5

0.4	1	0.57

0.4	1	0.57

0.41	1	0.58

0.5	1	0.66

0.5	1	0.66

0.5	1	0.66

0.5	1	0.66

0.5	1	0.66

0.5	1	0.66

0.55	1	0.71

0.57	1	0.72

0.57	1	0.72

0.6	0.6	0.6

0.6	0.75	0.66

0.6	1	0.74

0.6	1	0.75

0.66	0.5	0.57

0.66	0.66	0.66

0.66	0.8	0.72

0.66	1	0.8

0.66	1	0.8

0.66	1	0.8

0.66	1	0.8

0.66	1	0.8

0.66	1	0.8

0.66	1	0.8

0.66	1	0.8

0.75	0.75	0.75

0.75	1	0.85

0.75	1	0.85

0.8	0.8	0.8

0.8	1	0.88

0.8	1	0.88

0.83	1	0.9

0.83	1	0.9

0.83	1	0.9

0.83	1	0.9

0.83	1	0.9

1	0.25	0.4

1	0.33	0.5

1	0.66	0.8

1	0.75	0.85

1	1	1

1	1	1

1	1	1

1	1	1

1	1	1

1	1	1
