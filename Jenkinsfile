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
        stage('Checkout code from GitHub') {
            steps {
                git branch: 'dev',
                url:'https://github.com/mikuun/iTunes-API'
            }
        }
        stage('Run Smoke tests') {
            steps {
                sh 'npm install'
                sh 'npm run newman-smoke-tests'
            }
        }
        stage('Run full Postman collection') {
            steps {
                sh 'npm run newman-tests'
            }
        }
        stage('Build') {
            steps {
                echo "This is where the build would happen.."
            }
        }
    }
}
