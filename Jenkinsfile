pipeline {
    agent any
 
    stages {
 stage('Pull Repository') {
            steps {
                // Pull the repository source code from Git
                git branch: 'master', url: 'https://github.com/MedBouhdida1/jenkins.git'
            }
        }
   
        
        stage('Build docker image') {
            steps {
             script{
                bat 'docker build -t firstspring .'
             }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    bat 'docker run -d -p 8080:8080 firstspring'
                }
            }
        }
    }
}
