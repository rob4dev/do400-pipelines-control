node('nodejs') {
    stage('Checkout') {
        git branch: 'main', url: 'https://github.com/rob4dev/do400-pipelines-control'
    }
    stage('Backend tests') {
        sh 'node ./backend/test.js'
    }
    stage('Frontend tests') {
        sh 'node ./frontend/test.js'
    }
}