# Lambda-cicd

This repo basically consist of two github actions code.
The one which is triggered on a push request.We make the changes in our lambda function code and push it to github which then pushes it to lambda function on aws.

# Validate Cloudfromation template

The second github action code is to validate the cloudformation template on a pull request and deploy a cloud formation stack in the test environment if the validation is sucessful.
And on the merge of the pull request other job is ran which deletes the test stack deployed on test environmet
