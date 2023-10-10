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
                    sh 'docker build -t firstspring .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    // Run the Flask app in a Docker container within the workspace directory
                    sh 'docker run -d -p 8080:8080 firstspring'
                }
            }
        }
    }

    post {
        always {
            // Clean up - remove the Docker image locally (if necessary)
            script {
                // Optional: Remove the Docker image locally after the pipeline completes
                sh 'docker rmi firstspring'
            }
        }
    }
}
