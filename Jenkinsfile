pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/oliviya-s/python-jenkins-docker.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t python-app .'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'docker run python-app pytest'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run -d -p 5000:5000 python-app'
            }
        }
    }
}
