pipeline {
    environment {
        AWS_DEFAULT_REGION="us-east-1"
    }

    stages {
        stage ('init') {
            steps{
                
            }
        }

        stage ('Deploy to DEV'){
            withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'dev-serverless', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
                sh "serverless deploy --stage dev"
            }
        }

        stage ('System Test on Dev'){
             withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'dev-serverless', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
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