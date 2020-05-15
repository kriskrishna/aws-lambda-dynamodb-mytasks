pipeline {
    agent any
    stages {
        stage('hello AWS') {
            steps {
                withAWS(credentials: 'aws-credentials', region: 'us-east-1') {
                    sh 'echo "hello KB">hello.txt'
                    s3Upload acl: 'Private', bucket: 'kb-bucket', file: 'hello.txt'
                    s3Download bucket: 'kb-bucket', file: 'downloadedHello.txt', path: 'hello.txt'
                    sh 'cat downloadedHello.txt'
                }
            }
        }
    }
}