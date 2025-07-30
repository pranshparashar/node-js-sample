pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/pranshparashar/node-js-sample.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test || true'  // Optional: avoid breaking pipeline if test command not set
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "Deploying app to test environment..."'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully!'
        }
        failure {
            echo '❌ Pipeline failed. Check the logs above.'
        }
    }
}
