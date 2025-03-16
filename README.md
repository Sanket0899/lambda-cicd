# This repo basically consist of two github actions code.
# One that is triggered on a push event and other on a pull request event

## Lambda-cicd

This is the one which is triggered on a push request.We make the changes in our lambda function code in local and push it to github and the result to this push event an CICD pipeline is triggered which then pushes the lambda function code to aws lambda after sucessful validation.

## Validate Cloudformation template

The second github action code is to validate the cloudformation template on a pull request and deploy a cloud formation stack in the aws test environment if the validation of the template is sucessful.
And it consist of other job that on the merge of the pull request is ran and that deletes the test stack deployed on test environment

  ## How to run and validate the above code

  ### To push entire content on github
   git add .
   git commit -m " push"
   git push origin main
  
  
  ### Now as we are running the cicd pipeline on a pull request we will create a new branch
   git checkout -b branch_name
  
  ### Now make some changes in the cloud formation code and then push it to the new branch
   git add .
   git commit -m "made changes"
   git push
  git push --set-upstream origin update-cf
  
  ### Now a new pull request would be created in github go ahead and confirm the pull request this should trigger the first step in the job to create a stack using the cloud formation template.Go to AWS and validate if the cloudformation stack is deployed successfully once the CICD job 1 is completed.
  
  ### After validation and confirmation of the successful cloudformation stack go ahead and merge the pull request that will trigger the job 2 of the cicd code that is to delete the test stack that is created.Go to AWS and validate if the stack is deleted on successful completion of job 2 of the cicd pipeline



