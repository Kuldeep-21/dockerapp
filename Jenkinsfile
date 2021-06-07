pipeline {
    environment {
        registry = "coder21/dockerapp"
        registryCrendential = 'dockerhub_id'
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
                dockerImage= docker.build registry + ":$BUILD_NUMBER"
            }
        }
        stage('Deploy'){
            steps {
                docker.withRegistry('',registryCredential){
                    dockerImage.push()
                }
            }
        }
        
    }
    
    
}
