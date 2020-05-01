# Model Deployment with Sagemaker

To deploy a model, we establish an endpoint that allows the app and the model to exchange data/predictions.

Focus:
* Training and tuning XGBoost
* Creating model artifacts
* Testing with batch transform
* Deploying using endpoints created from API Gateway
* Preprocessing using AWS Lambda

We start an endpoint using the `.deploy()` method on an estimator, passing in some information about the instance, data type, etc.
