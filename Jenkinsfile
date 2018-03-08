pipeline {
    agent {
        docker {
            image 'node:8'
            args '-p 3000:3000 -p 5000:5000'
        }
    }
    environment {
        CI = 'true'
        npm_config_cache='npm-cache'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}

