pipeline {
    agent any
    stages {
        stage("instalacion dependencias"){
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
