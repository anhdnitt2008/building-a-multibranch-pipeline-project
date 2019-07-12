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
	stage('Deliver for development') {
             steps {
                sh './jenkins/scripts/deliver.sh'
		input message: 'Finished using the web site? (Click "Proceed" to continue)'
             }
        }
    }
}

