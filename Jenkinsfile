pipeline {
    agent any

    environment{
        USERNAME = "cmd"
    }
    stages {
        stage(" build - Instalacion dependencias"){
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
        stage("delivery - Subida a Nexus") {
            steps{
                script{
                    docker.withRegistry("http://localhost:8082" , "registry"){
                sh 'docker build -t backend-test .'
                sh 'docker tag backend-test:latest localhost:8082/backend-test:latest'
                sh 'docker push localhost:8082/backend-test:latest'
                }
            }
        }    
        }
    }
    }