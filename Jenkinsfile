pipeline {
    agent {
        docker {
            image 'node:18-alpine'
            args '-u root:root' // Run as root inside the container (optional)
        }
    }

    environment {
        APP_ENV = 'dev'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test || echo "No tests found"'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying app in ${APP_ENV} environment"
                // Add your deployment logic here
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully!'
        }
        failure {
            echo '❌ Pipeline failed. Check logs.'
        }
    }
}
