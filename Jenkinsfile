pipeline {
    agent any
    stages {
        stage('Setup Docker Permissions') {
            steps {
                sh 'sudo whoami'
                sh 'newgrp docker' // Attempts to refresh group membership
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-app:latest -f Dockerfile .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker run -d --name my-container my-app:latest'
            }
        }
    }
}
