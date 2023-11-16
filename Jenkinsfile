pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the Git repository
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Example build step (replace with your actual build command)
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Example test step (replace with your actual test command)
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded! Deploying to production...'
            // Add deployment steps here
        }
        failure {
            echo 'Pipeline failed! Notify the team...'
            // Add notification or rollback steps here
        }
    }
}
