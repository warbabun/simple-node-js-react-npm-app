pipeline {
    agent none
    
    stages {
        stage('BackEnd') { 
            agent {
                docker {
                    image 'mcr.microsoft.com/dotnet/core/sdk:3.1'
                    args '-u 0'
                }
            }
            steps {
                sh 'cd SimpleBackend && dotnet publish -c Release -o out'
            }
        }
        stage('FrontEnd') {
            agent {
                docker {
                    image 'node:12-alpine' 
                    args '--privileged=true --net host -v /var/run/dbus:/var/run/dbus -p 3000:3000'
                }
            }
            steps {
                sh 'cd SimpleFrontend && npm install' 
            }
        }
    }
}