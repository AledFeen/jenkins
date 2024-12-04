#!/usr/bin/env groovy
pipeline {
    agent any
    stages {
        stage('Install') {
            steps {
                echo 'Install dependencies..'
                bat 'npm install'
                bat 'npm install -g pm2 forever'
            }
        }
        stage('Stop all') {
            steps {
                echo 'Stop all..'
                bat 'chcp 65001 && forever stopall'  // Устанавливаем кодировку UTF-8 перед выполнением команды
            }
        }        
        stage('Deploy') {
            steps {
                echo 'Deploying.'
                bat 'set BUILD_ID=dontKillMe && pm2 start app.js'
            }
        }
    }
}
