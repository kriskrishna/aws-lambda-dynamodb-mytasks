pipeline {
    agent any
    stages {
      stage("Download Terraform") {
               // steps {
               //     sh 'curl https://releases.hashicorp.com/terraform/0.12.19/terraform_0.12.19_linux_amd64.zip --output terraform.zip'
               //     sh 'unzip terraform.zip -y'
               //     script {if (env.ENVIRONMENT == "prod") CONFIG_FILE = "prod"}
               // }
            }

                  stage("Initialise Terraform") {
                        steps {
                            configFileProvider([configFile(fileId: "terraform-provider-${CONFIG_FILE}", targetLocation: 'provider.tf')]) {
                                sh './terraform init'
                            }
                        }
                    }

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