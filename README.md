# Predict sentiment with LSTM on AWS

## Description

This is my final project for the [Deep Learning Nanodegree by Udacity](https://www.udacity.com/course/deep-learning-nanodegree--nd101)

In this project, I trained a LSTM model in PyTorch to classify movie reviews into positive and negative, and deploy the model to AWS with Amazon SageMaker and AWS Lambda. It was then surfaced on a simple webapp that lets people type in any body of text and the model would try to guess the sentiment of that text.

## The dataset

The dataset is composed of 25,000 movie reviews from IMDB, with negative and positive reviews equally split. The dataset can be found [here](https://ai.stanford.edu/~amaas/data/sentiment/), and the paper [here](https://ai.stanford.edu/~amaas/papers/wvSent_acl2011.pdf).

## The Model

I used a simple LSTM architecture, with 1 embedding layer, 1 LSTM layer, 1 Dense layer with a sigmoid function at the end. The hyper parameters are as follow:

| Hyperparameter      | Value |
| ------------------- | ----- |
| Embedding dimension | 32    |
| Hidden dimension    | 200   |
| Vocabulary size     | 5000  |

And below is the training configuration

| Configuration    | Value |
| ---------------- | ----- |
| Batch size       | 512   |
| Number of epochs | 10    |

## Repository structure

- Development and deployment of the model [SageMaker Project.ipynb](SageMaker%20Project.ipynb)
- The simple web app [index.html](index.html)

## How to reproduce

This project involves different components of the AWS ecosystem (EC2 compute engine, AWS Lambda, SageMaker, etc.), therefore the easiest way is to reproduce this on AWS instead on a local machine.

1. Create and AWS account (if you don't have one)
2. Login to AWS Console
3. Access SageMaker
4. Setup a notebook instance by clicking on **Create notebook instance** with the following details

    | Attribute              | Value                                              |
    | ---------------------- | -------------------------------------------------- |
    | Notebook instance type | ml.p2.xlarge                                       |
    | IAM Role               | New role > ... will provide access to `None`       |
    | Git repository         | `https://github.com/xquyvu/aws-sentiment-analysis` |

5. The other details should be set as default
6. Follow the steps in the [SageMaker Project.ipynb](SageMaker%20Project.ipynb) notebook
