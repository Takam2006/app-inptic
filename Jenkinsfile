pipeline {
    agent any

    stages {

        stage('Build Docker') {
            steps {
                sh 'docker build -t static-app .'
            }
        }

        stage('Run App') {
            steps {
                sh 'docker stop static-app || true'
                sh 'docker rm static-app || true'
                sh 'docker run -d -p 8085:80 --name static-app static-app'
            }
        }
    }
}
