# Machine Learning Engineering with AWS

This repository contains various template codes for training, testing, and deploying machine learning models with Amazon Sagemaker.

* Reference: Udacity's Github [repo](https://github.com/udacity/sagemaker-deployment) for Deep Learning Nanodegree

## Case study

Say we want to build a webapp that accepts a user's review. The entered review text data is sent off to an endpoint, created using API Gateway. The endpoint acts as an interface to a Lambda function that processes the user data and sends it off to the deployed model's endpoint. The deployed model performs inference on the processed data and returns the inference results to the Lambda function. The Lambda function returns the results to the original caller using the endpoint constructed using API Gateway. Lastly, the website receives the inference results and displays those results to the user.

Focus:
* _Notebook Instances_ provide a convenient place to process and explore data in addition to making it very easy to interact with the rest of SageMaker's features.

* _Training Jobs_ allow us to create model artifacts by fitting various machine learning models to data.

* _Hyperparameter Tuning_ allow us to create multiple training jobs each with different hyperparameters in order to find the hyperparameters that work best for a given problem.

* _Models_ are essentially a combination of model artifacts formed during a training job and an associated docker container (code) that is used to perform inference.

* _Endpoint Configurations_ act as blueprints for endpoints. They describe what sort of resources should be used when an endpoint is constructed along with which models should be used and, if multiple models are to be used, how the incoming data should be split up among the various models.

* _Endpoints_ are the actual HTTP URLs that are created by SageMaker and which have properties specified by their associated endpoint configurations. Have you shut down your endpoints?

* _Batch Transform_ is the method by which you can perform inference on a whole bunch of data at once. In contrast, setting up an endpoint allows you to perform inference on small amounts of data by sending it do the endpoint bit by bit.

* _S3_ as the central repository to store data (test/training/validation dataset and model artifacts created during training).

On a high level, we start an endpoint using the `.deploy()` method on an estimator, passing in some information about the instance, data type, etc. API Gateway gives a URL that can be used to invoke the API that facilitates communication between a web app and the model. A Lambda function handles the necessary preprocessing to convert the user request into something that the deployed model can understand.
