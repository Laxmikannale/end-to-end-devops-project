pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t laxmi-devops-website .'
            }
        }

        stage('Deploy Docker Container') {
            steps {
                sh 'docker rm -f website-container || true'
                sh 'docker run -d -p 80:80 --name website-container laxmi-devops-website'
            }
        }
    }
}
