# Model Deployment with Sagemaker

Say we want to build a webapp that accepts a user's review. The entered review text data is sent off to an endpoint, created using API Gateway. The endpoint acts as an interface to a Lambda function that processes the user data and sends it off to the deployed model's endpoint. The deployed model performs inference on the processed data and returns the inference results to the Lambda function. The Lambda function returns the results to the original caller using the endpoint constructed using API Gateway. Lastly, the website receives the inference results and displays those results to the user.

Focus:
* XGBoost
* Model Artifacts
* Batch Transform
* API Gateway
* AWS Lambda

On a high level, we start an endpoint using the `.deploy()` method on an estimator, passing in some information about the instance, data type, etc. API Gateway gives a URL that can be used to invoke the API that facilitates communication between a web app and the model. A Lambda function handles the necessary preprocessing to convert the user request into something that the deployed model can understand.
