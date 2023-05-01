
# Documentation to setup Jenkins CICD pipeline for this Application

## Clone the repository

- Run the following command to clone the repository:

```sh
git clone https://github.com/Chaitannyaa/node-todo-cicd.git
```

## Setting up webhooks

- Go to your GitHub repository and click on the "Settings" tab.
- Click on the "Webhooks" option in the left sidebar.
- Click on the "Add webhook" button.
- In the "Payload URL" field, enter the URL of the Jenkins server along with the path of the Jenkins webhook endpoint. 
  For example, "http://localhost:8080/github-webhook/".
- Select the events that you want to trigger the webhook.
- Click on the "Add webhook" button to save the webhook.

## Setting up Jenkins

- Download and install Jenkins on your server or local machine.
- Open Jenkins in your web browser and create a new pipeline job.
- Configure the pipeline job to use the GitHub repository that you cloned earlier.
- Add a build stage to the pipeline to build and test the application code.
- Add a deploy stage to the pipeline to deploy the application to your server.
- Configure the webhook in Jenkins to trigger the pipeline whenever there is a push event on the repository.

## Deploying the application
- Make changes to the code in your local repository.
- Commit and push the changes to the GitHub repository.
- The webhook will trigger the Jenkins pipeline, which will build and test the application code.
- If the build and tests pass, the pipeline will deploy the application to your server.
- You can monitor the status of the pipeline and any errors or failures in the Jenkins console.

## That's it! You now have a fully automated CI/CD pipeline that deploys your application whenever there is a new commit to your repository.
