pipeline {
    environment {
        AWS_ACCESS_KEY_ID = ${AWS_ACCESS_KEYID}
        AWS_SECRET_ACCESS_KEY = ${AWS_SECRET_ACCESSKEY}
    }

    stages {
        stage ('init') {
            steps{
                
            }
        }

        stage ('Deploy to DEV'){
            withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'AWS_DEV', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
                // some block
            }
        }

        stage ('System Test on Dev'){
             withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'AWS_DEV', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
                // some block
            }
        }

        stage('Deploy to SIT') {

        }

        stage('System Test on SIT') {

        }

        stage('Deploy to UAT'){

        }

        stage('System Test on UAT') {

        }

        stage('Approval'){
            
        }

        stage('Deploy to Prod'){

        }

        stage('Smoke Test'){

        }
    }
}