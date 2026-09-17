pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'sudo docker build -t laxmi-devops-website .'
            }
        }

        stage('Deploy Docker Container') {
            steps {
                sh 'sudo docker rm -f website-container || true'
                sh 'sudo docker run -d -p 80:80 --name website-container laxmi-devops-website'
            }
        }
    }
}
