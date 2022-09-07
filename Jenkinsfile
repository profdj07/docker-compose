
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                docker compose stop server
                docker compose rm server -f
                echo 'y' | docker image prune -a
                docker compose up -d
            }
        }
    }
}
