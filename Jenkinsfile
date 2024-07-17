pipeline {
    agent {
        node {
            label 'nodejs'
        }
    }
    parameters {
        booleanParam(name: "RUN_FRONTEND_TESTS", defaultValue: true)
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
                    when { expression { params.RUN_FRONTEND_TESTS } }
                    steps {
                        sh 'node ./frontend/test.js'
                    }
                }
            }
        }
    }
}
