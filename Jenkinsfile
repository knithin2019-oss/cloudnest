pipeline {

    agent any

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

        stage('List Files') {

            steps {

                sh '''
                ls -lh
                '''
            }

        }

    }

}