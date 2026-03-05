pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git 'https://github.com/samp80310/devops-end-to-end-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t samp80310/devops-demo-app:latest .'
            }
        }

        stage('Push to DockerHub') {
            steps {
                sh 'docker push samp80310/devops-demo-app:latest'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f kubernetes/deployment.yaml'
            }
        }

    }
}
