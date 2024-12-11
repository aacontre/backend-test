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
                stage("build - instalacion dependencias"){
                    steps{
                        sh 'npm install'
                    }
                
                 }    
                  stage("build - ejecucion de test"){
                    steps{
                        sh 'npm run test'
                    }
                
                 }               
                 stage("build - del proyecto"){
                    steps{
                        sh 'npm run build'
                    }
                 }
            }
        }     
     } 
}
 
