pipeline {
    agent any

    tools { nodejs "node"}

    environment {
            CI = 'true'
    }
    
    stages {
        stage('Build') {
            steps {
                bat 'npm install pm2 -g'
                bat 'npm install'
                bat 'npm install --global pm2@latest'
            }
        }
        stage('Test') {
                    steps {
                        bat './jenkins/scripts/test.bat'
                    }
                }
                stage('Deliver') {
                            steps {
                                bat './node_modules/pm2/bin/pm2 start src\\App.js --name myapp'

                            }
                        }

    }
}