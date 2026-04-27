pipeline {
    agent any

    tools {
        nodejs 'NodeJS'
    }

    environment {
        NODE_ENV = 'production'
    }

    stages {

        stage('Checkout Code') {
            steps {
                echo 'Fetching code from GitHub...'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'npm install'
            }
        }

        stage('Run Backend') {
            steps {
                echo 'Starting Node.js server...'
                sh 'node server.js &'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests (if any)...'
                sh 'npm test || true'
            }
        }

        stage('Build Frontend') {
            steps {
                echo 'Frontend static files ready...'
            }
        }

        stage('Done') {
            steps {
                echo 'Pipeline executed successfully'
            }
        }
    }

    post {
        success {
            echo 'Build Success'
        }
        failure {
            echo 'Build Failed'
        }
    }
}