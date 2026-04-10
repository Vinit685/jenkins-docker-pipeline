pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Vinit685/jenkins-docker-pipeline.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-docker-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker stop jenkins-docker-app || true'
                sh 'docker rm jenkins-docker-app || true'
                sh 'docker run -d -p 8082:80 --name jenkins-docker-app jenkins-docker-app'
            }
        }
    }
}

