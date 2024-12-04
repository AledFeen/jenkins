pipeline {
    agent any
    stages {
        stage('Check Files') {
            steps {
                bat 'if not exist package.json (exit /b 1)'
            }
        }
        stage('Install') {
            steps {
                echo 'Install..'
                bat 'npm install'
            }
        }
         stage('Stop all') {
            steps {
                echo 'Stop all..'
                bat 'forever stopall'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying..'
                bat 'set BUILD_ID=dontKillMe && pm2 start app.js'
            }
        }
    }
}
