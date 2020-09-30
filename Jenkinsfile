pipeline {
    agent {
        docker {
            image 'node:12-alpine' 
            args '--privileged=true --net host -v /var/run/dbus:/var/run/dbus -p 3000:3000'
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'cd SimpleFrontend && npm install' 
            }
        }
    }
}