pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "react-app:latest"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/amlan2601/jenkins.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build(DOCKER_IMAGE)
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    docker.image(DOCKER_IMAGE).run('-p 5000:5000')
                }
            }
        }
    }
}

