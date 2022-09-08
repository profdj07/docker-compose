pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh 'whoami && pwd'
                sh 'docker-compose stop server'
                sh 'docker-compose rm server -f'
                sh 'echo "y" | docker image prune -a'
                sh 'docker-compose up -d'
            }
        }
        stage('SCP'){
            steps{
                 sshagent(credentials: ['Server-Docker-Compose']) {
            sh '''ssh -i ~/.ssh/dev_iam.pem ubuntu@43.204.144.35 \" ls\"

            '''
          }
                }
            }
        }
    }
}

