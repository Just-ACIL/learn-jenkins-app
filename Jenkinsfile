pipeline {
    agent any

    stages {
        stage('Hello') {
            agent{
                docker {
                    image "node:18-alpine"
                    reuseNode true
                }
            }
            steps {
                sh '''
                ls -la
                node --version
                npm --version
               
                ls -la
                '''
            }
        }
        stage("Test"){
            steps{
                sh '''
                test -f build/index.html
                npm test
                '''
            }
        }
    }
}