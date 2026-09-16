pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out the project code...'
            }
        }

        stage('Build') {
            steps {
                echo 'Build started...'
                echo 'Build successful!'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing application...'
                echo 'Tests completed successfully!'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment stage...'
                echo 'Deployment successful!'
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Check the console output.'
        }
    }
}
