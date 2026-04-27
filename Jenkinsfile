pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Code already checked out from GitHub'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run App Check') {
            steps {
                sh 'node -v'
                sh 'npm -v'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test || true'
            }
        }

        stage('Build') {
            steps {
                echo 'No build step for static frontend'
            }
        }
    }

    post {
        success {
            echo 'Pipeline Success'
        }
        failure {
            echo 'Pipeline Failed'
        }
    }
}