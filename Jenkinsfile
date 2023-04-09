#!/usr/bin/env groovy
pipeline {
    agent any
    tools {
        maven 'maven'
    }
    environment {
       IMAGE_TAG = '1.1.2'                              
   }
  stages {
        stage('build') {
            steps {
                script {
                    echo 'incrementing adservice microservices version...'

                    
                }
            }
        }
        
        stage('build, and Push image ') {
            
            steps {
                script {
                    echo "building the docker image..."

                     withDockerRegistry([ credentialsId: "ACR", url: "microservicesb.azurecr.io" ]) {
                        
                        sh " docker build -t microservicesb.azurecr.io/emailservice:${env.IMAGE_TAG} ./src/emailservice/  " 
                        
        
                    }
                }
            }
        }


}
}