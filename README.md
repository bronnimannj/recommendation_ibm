# recommendation_ibm

## Table of contents

- [Motivations](#motivations)
- [Packages used](#packages_used)
- [Files](#files)
- [Analysis workflow](#analysis_workflow)

## Motivations <a name="motivations"></a>

This project is part of the nanodegree [become a data scientist](https://eu.udacity.com/course/data-scientist-nanodegree--nd025) of [Udacity](https://eu.udacity.com/).

In this project, I am creating a recommendation engine with Watson Studio Data from IBM.


## Packages used <a name="packages_used"></a>

- pandas
- numpy
- matplotlib
- pickle
- re
- nltk
- pathlib
- os
- sys

## Files <a name="files"></a>

Here is the content of this repo:

```text

- data
|-articles_community.csv
|-user_item_interactions.csv

- notebooks
|- recommendation_pipeline.ipynb # Notebook to run the recommendation engine
|- recommendation_pipeline.html # hardcore HTML version of the notebook

- tests
|- __init__.py # an init file to call this folder as a module
|- project_tests.py # file containing the tests for this project
|- top_5.p # file used for tests
|- top_10.p # file used for tests
|- top_20.p # file used for tests
|- user_item_matrix.p # file used for tests

- LICENSE
- README.md
- .gitignore

```

The jupyter notebook includes the following steps:

1. An EDA
2. A Rank Based recommendation engine
3. A User-user-based collaborative filtering engine
4. A Matrix factorization engine

See next section for more details on the workflow.

## Analysis workflow <a name="analysis_workflow"></a>

Here are the details of the steps taken in the notebook.

### Exploratory Data Analysis (EDA)

To get started in building recommendations, I first identified the most popular articles simply based on users interaction. Since there are no ratings for any of those articles, it made sense to assume that articles with the most interactions are the most popular. These are then the articles we might recommend to new users (or anyone depending on what we know about them).

### Rank Based recommendation engine

In order to build better recommendations for the users of IBM's platform, I took a look at users that are similar in terms of the items they have interacted with. These items could then be recommended to the similar users. This would be a step in the right direction towards more personal recommendations for the users.


### User-user-based collaborative filtering engine

Given the amount of content available for each article, there are a number of different ways in which someone might choose to implement a content based recommendations system. I utilized NLP to develop a content based recommendation system. This system goes through each article title and finds the most common words(related to a content) throughout all the available articles and recommends articles based on the sum of matched words in the title of an article and popularity.

### Matrix factorization engine

Matrix decomposition is used to predict new articles an individual might interact with.