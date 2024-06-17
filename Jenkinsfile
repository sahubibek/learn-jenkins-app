pipeline {
    agent any
    parameters {
        string(name: 'GREETING', defaultValue: 'Hello', description: 'The greeting to use')
    }
    stages {
                stage('Deploy') {
            steps {
                echo 'Deploying ...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing ...'
            }
        }
        
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}
