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
                sh 'npm install'
                sh 'npm newman run iTunesAPI.postman_collection.json'
            }
        }
        stage('Unit Test') {
            steps {
              echo "Unit test..."
                // sh 'npm test -- --coverage'
            }
        }
    }
}
