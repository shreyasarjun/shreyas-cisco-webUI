pipeline {
    agent any

    stages {
        stage('Fetching source code from github') {
            steps {
                echo 'github source code pulling'
                git 'https://github.com/shreyasarjun/shreyas-cisco-webUI.git'
                sh 'ls'
                sh 'java -version'
            }
        }
        stage('Building docker image and create container') {
            steps {
                echo 'Running docker command'
                sh 'docker-compose up -d --build'
                sh 'docker-compose ps'
                sh 'docker images'
            }
        }
        stage('Testin container status by access page') {
            steps {
                sh 'curl -f http://localhost:4000/health.html'
                echo 'health page is working fine'
            }
        }
    }
}
