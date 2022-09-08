
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
                withCredentials([sshUserPrivateKey(credentialsId: 'Server-Docker-Compose', keyFileVariable: 'dev_iam.pem')]) {
                    sh """ssh -t ubuntu@43.204.144.35 \' mkdir ssh1 \' """
                }
            }
        }
    }
}
