pipeline{
    agent any
    stages{
        stage('build'){
            steps {
                
                echo 'building the pipeline'
            }
            
        }
        stage('Building Docker Image'){
            steps {
                bat 'docker build.-t aditya-12-app:latest'
                echo 'starting the app'
            }
        }
        stage('run the conatiner image'){
            steps {
                sh 'docker rm aditya-12-container || exit 0'
                sh 'docker run -d --name aditya-12-container -p 8081:80 aditya-12-app:latest '
            }
        }
        
        
    }
}
