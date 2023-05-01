pipeline {
    agent any
    
    stages{
        stage ("code"){
            steps {
                git url: 'https://github.com/Chaitannyaa/node-todo-cicd.git', branch: 'master'
            }
        }
        stage ("Build"){
            steps {
                sh 'docker build -t chaitannyaa/node-todo-app-cicd:latest .'
            }
        }
        stage ("login and push image"){
            steps {
                echo 'Logging into docker and pushing an image on dockerhub'
                withCredentials([usernamePassword(credentialsId: 'DockerHub', passwordVariable: 'password', usernameVariable: 'user')]) {
                    sh "docker login -u ${env.user} -p ${env.password}"
                    sh "docker push chaitannyaa/node-todo-app-cicd:latest"
                }
            }
        }
        stage ("Deploy"){
            steps {
                sh 'docker-compose down && docker-compose up -d'
            }
        }
    }
}
