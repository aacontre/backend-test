pipeline {
    agent any
    stages {
        stage("instalacion dependencias"){
            agent {
                docker {
                    image 'node:22-alpine'
                    reuseNode true
                }
            }
            stages{
                stage("instalacion dependencias despues de docker")
                    steps{
                        sh 'npm install'
                    }
                
                 }            
                 stage("build del proyecto"){
                    steps{
                        sh 'npm run build'
                 }
        
             }
            }
           }     
        }
 
