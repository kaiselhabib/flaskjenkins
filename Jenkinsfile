pipeline {
    agent any

    stages {
        stage('Pull Repository') {
            steps {
                // Pull the repository source code from Git into the workspace
                git branch: 'main', url: 'https://github.com/Ibrahimkarray/flaskjenkins.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image within the workspace directory
                    sh 'docker build -t jenkinsflask .'
                }
            
        }
        }

        stage('Run Docker Container') {
            steps {
                
                script {
                    // Run the Flask app in a Docker container within the workspace directory
                    sh 'docker run -d -p 5000:5000 jenkinsflask'
                }
            
            }
        }
    }

    post {
        always {
            // Clean up - remove the Docker image locally (if necessary)
            script {
                // Optional: Remove the Docker image locally after the pipeline completes
                sh 'docker rmi jenkinsflask'
            }
        }
    }
}
