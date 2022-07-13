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
            }
        }
        stage('Test') {
                    steps {
                        bat './jenkins/scripts/test.bat'
                    }
                }
                stage('Deliver') {
                            steps {
                                bat 'pm2 start src\\App.js --name myapp'

                            }
                        }

    }
}