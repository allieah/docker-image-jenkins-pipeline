pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Cloning the repository
                bat '''https://github.com/allieah/docker-image-jenkins-pipeline.git
git checkout main 
'''
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    // Building the Docker image
                    bat 'docker build -t myapp:latest .'
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    // Running the Docker container in daemon mode
                    bat 'docker run -d --name myapp-container myapp:latest'
                }
            }
        }
    }
    post {
        always {
            // Cleanup or notification steps
            bat 'echo \'Pipeline execution completed.\''
        }
    }
}
