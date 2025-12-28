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
        sshagent(['ubuntu']) {
        sh ''' 
        scp target/hello.war ubuntu@13.126.223.241:/home/ubuntu/app/

            ssh ubuntu@13.126.223.241 "nohup java -jar /home/ubuntu/app/hello.war \
                > /home/ubuntu/app &"
        '''
        }
    }
}

        }
    }


