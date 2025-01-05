# This repo basically consist of two github actions code.
# One that is triggered on a push event and other on a pull request event

## Lambda-cicd

This is the one which is triggered on a push request.We make the changes in our lambda function code in local and push it to github and the result to this push event an CICD pipeline is triggered which then pushes the lambda function code to aws lambda after sucessful validation.

## Validate Cloudfromation template

The second github action code is to validate the cloudformation template on a pull request and deploy a cloud formation stack in the aws test environment if the validation of the template is sucessful.
And it consist of other job that on the merge of the pull request is ran and that deletes the test stack deployed on test environment
