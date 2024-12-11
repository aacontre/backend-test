pipeline {
    agent any

    environment{
        USERNAME = "cmd"
    }
    stages {
        stage(" build - Crear imagen en docker"){
            agent {
                docker {
                    image 'node:22-alpine'
                    reuseNode true
                }
            }
            stages{
                stage("build - Instalacion dependencias"){
                    steps{
                        sh 'npm install'
                    }
                
                 }    
                  stage("build - Ejecucion de test"){
                    steps{
                        sh 'npm run test'
                    }
                
                 }               
                 stage("build - Compilar el proyecto"){
                    steps{
                        sh 'npm run build'
                    }
                 }
            }
        }     
     } 
}
 
