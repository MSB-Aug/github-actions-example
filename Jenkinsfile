pipeline {
    agent any
    stages {
        stage('checkouthecode') {
            steps {
              git 'https://github.com/MSB-Aug/github-actions-example.git'   
            }
        }
        stage('builddockerimage') {
            steps {
              sh "mvn install"
              sh "docker build -t nginxapp:1 ." 
             
            }
        }
        
        stage('creating a container') {
            steps {
              sh "docker --version"
              sh "docker rm -f nginxcontainer"
              sh "docker run -d --name nginxcontainer -p 500:80 nginxapp:1" 
            }
        }
    }
}
