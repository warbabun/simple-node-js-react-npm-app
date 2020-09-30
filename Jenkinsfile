pipeline {
    agent {
        docker {
            image 'node:12-alpine' 
            args '-p 3000:3000 --privileged --network=jenkins'
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install --loglevel verbose' 
            }
        }
    }
}