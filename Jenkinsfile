pipeline {
    agent any
 
    stages {
 stage('Pull Repository') {
            steps {
                // Pull the repository source code from Git
                git branch: 'main', url: 'https://github.com/Ibrahimkarray/flaskjenkins.git'
            }
        }
   
        
        stage('Build docker image') {
            steps {
             script{
                sh 'docker build -t firstspring .'
             }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker run -d -p 8080:8080 firstspring'
                }
            }
        }
    }
}
