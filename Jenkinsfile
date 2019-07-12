pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3002:3002 -p 5000:5000'
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
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
            }
        }
    }
}
