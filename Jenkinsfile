pipeline {
    agent any
    stages {
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
        stage('Cleanup') {
            steps {
                sh 'docker stop my-container'
                sh 'docker rm my-container'
            }
        }
    }
}
