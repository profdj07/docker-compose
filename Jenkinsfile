
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
               
                sh 'docker compose stop server'
                sh 'docker compose rm server -f'
                sh 'echo "y" | docker image prune -a'
                sh 'docker compose up -d'
            }
        }
    }
}
