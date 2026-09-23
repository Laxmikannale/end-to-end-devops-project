pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub-credentials')
    }

    stages {

        stage('GitHub Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Laxmikannale/end-to-end-devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t laxmikannale/laxmi-devops-website:latest .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                sh 'docker push laxmikannale/laxmi-devops-website:latest'
            }
        }

        stage('Ansible Deployment') {
            steps {
                sh 'ansible-playbook -i ansible/inventory.ini ansible/deploy.yml'
            }
        }
    }
}
