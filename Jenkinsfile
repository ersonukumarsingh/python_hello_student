pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
               
                echo 'Checking out source code...'
            }
        }
        
        stage('Build Image') {
            steps {
                echo 'Building Docker Image...'
                
                sh 'docker build -t python_hello_student .'
            }
        }
        
        stage('Run Container') {
            steps {
                echo 'Running Docker Container...'
                
                sh 'docker stop python_container || true'
                sh 'docker rm python_container || true'
                
                
                sh 'docker run -d -p 5000:5000 --name python_container python_hello_student'
            }
        }
    }
}