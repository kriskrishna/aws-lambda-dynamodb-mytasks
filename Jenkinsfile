pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION="us-east-1"
    }

    stages {
        
        stage ('Deploy to DEV') {

            steps {
                withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'dev-serverless', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
                    sh "serverless deploy --stage dev"
                }
            }
        }

        stage ('System Test on Dev') {
             
             steps {
                export TASKS_ENDPOINT=6pgn5wuqeh.execute-api.us-east-1.amazonaws.com/dev
                withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'dev-serverless', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
                    sh ''' 
                       npm install --no-bin-links
                       ./node_modules/mocha/bin/mocha ./test/*.js
                    '''
                }
             }
        }

    }
}