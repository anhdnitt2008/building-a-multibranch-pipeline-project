pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3003:3003' 
        }
    }
    environment {
        HOME = '.'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage(’Deploy for master’) {
            steps {
                sh ’npm start’
            }
        }
    }
}

