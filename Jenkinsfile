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

            steps{
                withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'dev-serverless', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
                    sh "serverless deploy --stage dev"
                }
            }
        }

        stage ('System Test on Dev'){
             
             steps{

                withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'dev-serverless', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
                    // some block
                }
             }
        }

        stage('Deploy to SIT') {

            steps{
                
            }

        }

        stage('System Test on SIT') {

            steps{
                
            }

        }

        stage('Deploy to UAT'){

            steps{
                
            }

        }

        stage('System Test on UAT') {

            steps{
                
            }

        }

        stage('Approval'){

            steps{
                
            }
            
        }

        stage('Deploy to Prod'){
            steps{
                
            }
        }

        stage('Smoke Test'){
            steps{
                
            }

        }
    }
}