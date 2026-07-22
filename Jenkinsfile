pipeline {
    agent any

    stages {
        stage('Build Image') {
            steps {
                sh 'docker build -t portfolio .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                docker rm -f portfolio-container || true
                docker run -d -p 3500:80 --name portfolio-container portfolio
                '''
            }
        }
    }
}