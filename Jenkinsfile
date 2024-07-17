pipeline {
    agent {
        node {
            label 'nodejs'
        }
    }

    stages {
        stage('Run tests') {
            parallel {
                stage('Backend tests') {
                    steps {
                        sh 'node ./backend/test.js'
                    }
                }
                stage('Frontend tests') {
                    steps {
                        sh 'node ./frontend/test.js'
                    }
                }
            }
        }
    }
}
