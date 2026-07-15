pipeline {

    agent any

    environment {
        BUCKET = "cloudnest-artifacts-nithin"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/knithin2019-oss/cloudnest.git'
            }
        }

        stage('Build WAR') {
            steps {
                sh '''
                jar -cvf cloudnest.war *
                '''
            }
        }

        stage('Upload Artifact') {
            steps {
                sh '''
                aws s3 cp cloudnest.war s3://$BUCKET/
                '''
            }
        }

    }

}