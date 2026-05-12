pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/YOUR_USERNAME/devops-pipeline-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t website .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop website || true'
                sh 'docker rm website || true'
            }
        }

        stage('Deploy New Container') {
            steps {
                sh 'docker run -d -p 80:80 --name website website'
            }
        }
    }
}
