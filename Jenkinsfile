pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/arunkumarsenthilkumar25-dev/CICD-Pipeline.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-website .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker stop devops-container || true'
                sh 'docker rm devops-container || true'
                sh 'docker run -d -p 80:80 --name devops-container devops-website'
            }
        }

    }
}
