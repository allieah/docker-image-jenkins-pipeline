pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Jenkins automatically handles Git operations based on job configuration
                echo 'Checked out the code'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    // Ensure Docker daemon is running and accessible
                    bat 'docker build -t myapp:latest .'
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    // Ensure Docker container runs properly
                    bat 'docker run -d --name myapp-container myapp:latest'
                }
            }
        }
    }
    post {
        always {
            // Cleanup or notification steps
            bat 'echo Pipeline execution completed.'
        }
    }
}
