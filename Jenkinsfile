pipeline {
    agent any

    environment {
        IMAGE_NAME = 'simple-node-app'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git url: 'https://github.com/sudo-subham/devops-assessment.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Deploy Application') {
            steps {
                sh 'docker compose down'
                sh 'docker compose up -d'
            }
        }
    }
}
