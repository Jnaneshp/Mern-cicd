pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Deploy Application') {
            steps {
                bat 'docker-compose down'
                bat 'docker-compose up -d --build'
            }
        }

        stage('Verify Running Containers') {
            steps {
                bat 'docker ps'
            }
        }
    }
}
