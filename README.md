# Model Deployment with Sagemaker

Focus:
* XGBoost
* Model Artifacts
* Batch Transform
* API Gateway
* AWS Lambda

On a high level, we start an endpoint using the `.deploy()` method on an estimator, passing in some information about the instance, data type, etc. API Gateway gives a URL that can be used to invoke the API that facilitates communication between a web app and the model. A Lambda function handles the necessary preprocessing to convert the user request into something that the deployed model can understand.
