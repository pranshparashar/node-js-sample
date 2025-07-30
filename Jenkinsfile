pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git bransh: 'main', https://github.com/pranshparashar/node-js-sample.git
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Deploy (Simulate)') {
            steps {
                sh 'echo "Deploying app to test environment..."'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check logs!'
        }
    }
}
