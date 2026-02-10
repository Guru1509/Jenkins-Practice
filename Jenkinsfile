pipeline {
    agent any

    environment {
        PATH = "/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin"
        DOCKER = "docker"
    }

    stages {
        stage('Build Docker Image') {
            steps {
                sh '$DOCKER build -t python-app .'
            }
        }

        stage('Run Tests Inside Docker') {
            steps {
                sh '$DOCKER run --rm python-app pytest'
            }
        }

        stage('Run Application') {
            steps {
                sh '$DOCKER run --rm python-app'
            }
        }
    }
}