
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the pipeline'
            }
        }

        stage('Building Docker Image') {
            steps {
                sh 'docker build -t aditya-12-app:latest .'
                echo 'Docker image built successfully'
            }
        }

        stage('Run the Container Image') {
            steps {
                sh 'docker rm -f aditya-12-container || true'
                sh 'docker run -d --name aditya-12-container -p 8081:80 aditya-12-app:latest'
            }
        }
    }
}
