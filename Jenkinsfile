#!/usr/bin/env groovy
pipeline {
    agent any
    tools {
        maven 'maven'
    }
    environment {
        ACR_REPO_URL = 'microservicesb.azurecr.io'
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
        
        stage('build image') {
            steps {
                script {
                    echo "building the docker image..."
                    withCredentials([usernamePassword(credentialsId: 'ACR', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                        
                        sh "echo $PASS | docker login -u $USER --password-stdin ${ACR_REPO_URL}"

                        sh " docker build -t microservicesb.azurecr.io/emailservice:${IMAGE_TAG} ./src/emailservice/  " 
                        sh "docker push  microservicesb.azurecr.io/emailservice:${IMAGE_TAG} "
                        

                        sh " docker build -t microservicesb.azurecr.io/currencyservice:${IMAGE_TAG} ./src/currencyservice/ "
                        sh " docker push  microservicesb.azurecr.io/currencyservice:${IMAGE_TAG} "
                        
                        sh " docker build -t microservicesb.azurecr.io/paymentservice:${IMAGE_TAG} ./src/paymentservice/ "
                        sh "docker push microservicesb.azurecr.io/paymentservice:${IMAGE_TAG} "
                    }
                }
            }
        }




}
}