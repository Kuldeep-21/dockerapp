pipeline {
    environment {
        registry = "coder21/dockerapp"
        registryCrendential = 'Dockerhub'
        dockerImage = ''
    }
    
    agent any
    stages {
        stage('Git Cloning'){
            steps {
            git 'https://github.com/Kuldeep-21/dockerapp.git'
            }
        }
        stage('Building Image'){
            steps {
                sh "docker build -t coder21/dokcerapp ."
            }
        }
        stage('pushing Image to DockerHub'){
            steps {
                docker.withRegistry('',registryCredential){
                    sh "docker push coder21/dockerapp"
                }
            }
        }
        
    }
    
    
}
