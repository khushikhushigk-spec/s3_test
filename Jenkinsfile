pipeline {
    agent any
 
    environment {
        AWS_DEFAULT_REGION = 'eu-north-1'
        S3_BUCKET = 'etsaw'
        S3_FILE = 's3://etsaw/myapp.war'
        LOCAL_FILE = 'file.zip'
    }
 
    stages {
        stage('Download from S3') {
            steps {
                withCredentials([[
                    $class: 'AmazonWebServicesCredentialsBinding',
                    credentialsId: 'aws_cred'
                ]]) {
                    bat '''
                        aws s3 ls
                        aws s3 cp s3://etsaw/myapp.war f2.md C:\\
                    '''
                }
            }
        }
    }
}
