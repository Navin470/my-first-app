pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/Navin470/my-first-app.git'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t html-app:v1 .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}