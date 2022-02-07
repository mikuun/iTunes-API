pipeline {
    agent any
    tools { nodejs "nodejs" }
    
    stages {
        stage('Tools initiated') {
            steps {
                sh 'npm -v'
                sh 'git --version'
            }
        }
        stage('Checkout code') {
            steps {
                git branch: 'main',
                url:'https://github.com/mikuun/iTunes-API'
            }
        }
        stage('Build') {
            steps {
                echo 'Build by running the postman scripts from file'
                sh 'npm install'
                //sh 'newman run iTunesAPI.postman_collection.json'
                sh 'npm run newman-tests'
            }
        }
    }
}
