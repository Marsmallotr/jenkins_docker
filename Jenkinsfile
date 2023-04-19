pipeline {
    agent any
    stages {
        stage('Clone'){
            steps{
                git 'https://github.com/Marsmallotr/jenkins_docker.git'
                sh 'cat Dockerfile'
            }
        }

        stage('Build Docker Image'){
            steps {
                sh 'docker build --add-host=docker:192.168.1.65 -t simple_docker .'
            }
        }

        stage('Run Docker Container'){
            steps {
                sh 'docker run -d -p 5000:5000 simple_docker'
            }
        }
    }
}