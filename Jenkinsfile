pipeline {
    agent any
    stages {
        stage('GitHub Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/YOUR_USERNAME/end-to-end-devops-project.git'
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Build Successful"'
            }
        }
    }
}
