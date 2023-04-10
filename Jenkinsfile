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
        
        stage(' build images ') {
            steps {
                script {
                    echo "building the docker image..."
                    withCredentials([usernamePassword(credentialsId: 'ACR', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                        
                        // sh "echo $PASS | docker login -u $USER --password-stdin ${ACR_REPO_URL}"

                        // // emailservice
                        // sh " docker build -t microservicesb.azurecr.io/emailservice:${IMAGE_TAG} ./src/emailservice/  " 
                        // sh " docker push  microservicesb.azurecr.io/emailservice:${IMAGE_TAG} "
                        
                        // // currencyservice
                        // sh " docker build -t microservicesb.azurecr.io/currencyservice:${IMAGE_TAG} ./src/currencyservice/ "
                        // sh " docker push  microservicesb.azurecr.io/currencyservice:${IMAGE_TAG} "
                        
                        // // paymentservice
                        // sh " docker build -t microservicesb.azurecr.io/paymentservice:${IMAGE_TAG} ./src/paymentservice/ "
                        // sh " docker push microservicesb.azurecr.io/paymentservice:${IMAGE_TAG} "
                        
                        // // recommendationservice
                        // sh " docker build -t microservicesb.azurecr.io/recommendationservice:${IMAGE_TAG} ./src/recommendationservice/ "
                        // sh " docker push microservicesb.azurecr.io/recommendationservice:${IMAGE_TAG}  "

                        // // productcatalogservice
                        // sh " docker build -t microservicesb.azurecr.io/productcatalogservice:${IMAGE_TAG} ./src/productcatalogservice/ "
                        // sh " docker push  microservicesb.azurecr.io/productcatalogservice:${IMAGE_TAG} "
                      
                        // // cartservice
                        // sh " docker build -t microservicesb.azurecr.io/cartservice:${IMAGE_TAG} ./src/cartservice/src " 
                        // sh " docker push microservicesb.azurecr.io/cartservice:${IMAGE_TAG} " 

                        // adservice
                        // sh " docker build -t microservicesb.azurecr.io/adservice:${IMAGE_TAG} ./src/adservice/ " 
                        // sh " docker push microservicesb.azurecr.io/adservice:${IMAGE_TAG}  " 
                       
                        // checkoutservice
                        sh " docker build -t microservicesb.azurecr.io/checkoutservice:${IMAGE_TAG} ./src/checkoutservice/  " 
                        sh " docker push microservicesb.azurecr.io/checkoutservice:${IMAGE_TAG}   " 
                    
                    }
                }
            }
        }




}
}