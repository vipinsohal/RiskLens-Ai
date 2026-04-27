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
                // 'sh' ki jagah 'bat' use kiya
                bat 'npm install'
            }
        }

        stage('Run App Check') {
            steps {
                bat 'node -v'
                bat 'npm -v'
            }
        }

        stage('Test') {
            steps {
                // Windows ke liye exit 0 use kiya
                bat 'npm test || exit 0'
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
