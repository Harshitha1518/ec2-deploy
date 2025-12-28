pipeline {
    agent any

    tools {
        maven 'M3'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Harshitha1518/ec2-deploy.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
            sh '''
            cp target/myapp.war ubuntu@13.126.223.241:/home/ubuntu/app/
            '''
                }
            }
        }
    }


