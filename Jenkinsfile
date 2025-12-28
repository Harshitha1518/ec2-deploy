pipeline {
    agent any

    tools {
        maven 'maven3'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Harshitha1518/ec2-deploy.git'
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
            mkdir -p /home/ubuntu/app
            cp target/myapp.war ubuntu@13.126.223.241:/home/ubuntu/app/
            '''
                }
            }
        }
    }
}

