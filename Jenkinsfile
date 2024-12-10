pipeline {
    agent any
    stages {
        stage("instalación dependencias"){
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
