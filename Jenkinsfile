pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t python-app .'
            }
        }

        stage('Run Tests Inside Docker') {
            steps {
                sh 'docker run --rm python-app pytest'
            }
        }

        stage('Run Application') {
            steps {
                sh 'docker run --rm python-app'
            }
        }
    }
}