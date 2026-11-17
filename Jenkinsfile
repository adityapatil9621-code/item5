
pipeline {
    agent any

    environment {
        DOCKER = '/Users/aditya/.docker/bin/docker'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the pipeline'
            }
        }

        stage('Check Docker') {
            steps {
                sh '${DOCKER} version'
            }
        }

        stage('Building Docker Image') {
            steps {
                sh '${DOCKER} build -t aditya-12-app:latest .'
                echo 'Docker image built successfully'
            }
        }

        stage('Run the Container Image') {
            steps {
                sh '${DOCKER} rm -f aditya-12-container || true'
                sh '${DOCKER} run -d --name aditya-12-container -p 8081:80 aditya-12-app:latest'
            }
        }
    }
}
