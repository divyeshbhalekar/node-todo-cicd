# Documentation to setup Jenkins CICD pipeline for this Application

## Clone the repository

- Run the following command to clone the repository:

```sh
git clone https://github.com/Chaitannyaa/node-todo-cicd.git
```

## Setting up webhooks

- Go to your GitHub repository and click on the "Settings" tab.

![image](https://user-images.githubusercontent.com/117350787/235436622-a6be4b78-2650-415e-aa5c-19ba81293454.png)

- Click on the "Webhooks" option in the left sidebar.

![image](https://user-images.githubusercontent.com/117350787/235436693-30bdae6a-101f-4ba8-90e6-f4f789e90dea.png)

- Click on the "Add webhook" button.

![image](https://user-images.githubusercontent.com/117350787/235436914-a20b4473-0536-4c5f-af55-149bc1b76113.png)

- In the "Payload URL" field, enter the URL of the Jenkins server along with the path of the Jenkins webhook endpoint. For example, "http://localhost:8080/github-webhook/".

![image](https://user-images.githubusercontent.com/117350787/235436791-10a24ca9-9c2a-4495-8660-534eec7e9374.png)

- Select the events that you want to trigger the webhook.

![image](https://user-images.githubusercontent.com/117350787/235436920-64008385-6f70-4ab2-af90-4a49ebc753fe.png)

- Click on the "Add webhook" button to save the webhook.

![image](https://user-images.githubusercontent.com/117350787/235437014-ee4cacbb-e82a-4f19-a115-a86ee189c2ca.png)

## Setting up Jenkins

- Download and install Jenkins on your server or local machine.

[Read my blog >>](https://90daysofdevopschallenge.hashnode.dev/day07-90daysofdevops-challenge-tws)

- Setup jenkins server by installing dependencies
```sh
sudo apt  install docker.io
```
```sh
sudo apt  install docker-compose
```
```sh
sudo usermod -aG docker $USER
```
```sh
sudo usermod -aG docker jenkins
```
```sh
sudo reboot
```

- Open Jenkins in your web browser and create a new pipeline job.

![image](https://user-images.githubusercontent.com/117350787/235436303-49db3a4c-02b4-4371-96bb-992968e1c80b.png)

![image](https://user-images.githubusercontent.com/117350787/235436426-96cc67cd-6430-4b34-9d80-2a75fbc3d18c.png)

- Configure the pipeline job to use the GitHub repository that you cloned earlier.

![image](https://user-images.githubusercontent.com/117350787/235437278-6959c2a7-d81e-4868-baad-3539651cae57.png)

- Add a build stage to the pipeline to build and test the application code.

![image](https://user-images.githubusercontent.com/117350787/235437449-ff14d143-f9a4-4881-ad38-64abce1a9d23.png)

- Add a deploy stage to the pipeline to deploy the application to your server.

![image](https://user-images.githubusercontent.com/117350787/235437500-9ead72e6-e063-4866-ae69-df17091b81a3.png)

- Configure the webhook in Jenkins to trigger the pipeline whenever there is a push event on the repository.

![image](https://user-images.githubusercontent.com/117350787/235437552-433f6ce2-3024-49e0-80dd-fc0c605ced42.png)

## Deploying the application

- Make changes to the code, Commit and push the changes to the GitHub repository.

![image](https://user-images.githubusercontent.com/117350787/235441155-f642991d-1440-4cc5-b3d2-eaff928b7927.png)

- The webhook will trigger the Jenkins pipeline, which will build and test the application code.

![image](https://user-images.githubusercontent.com/117350787/235441473-d7a38494-624a-4aed-bee2-d2b05c2fc158.png)

- If the build and tests pass, the pipeline will deploy the application to your server.

![image](https://user-images.githubusercontent.com/117350787/235441310-be0cf1a1-abad-43e9-a7ab-eaf639bb5328.png)

![image](https://user-images.githubusercontent.com/117350787/235441522-d7fdf3e3-7123-4a05-bf65-c2639aba6bd5.png)

- You can monitor the status of the pipeline and any errors or failures in the Jenkins console.

![image](https://user-images.githubusercontent.com/117350787/235441686-6cbf392c-f165-4f16-9f7a-35e6015a0584.png)


## That's it! You now have a fully automated CI/CD pipeline that deploys your application whenever there is a new commit to your repository.
