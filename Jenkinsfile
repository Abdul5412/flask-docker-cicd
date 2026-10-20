pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out Flask Docker CI/CD project'
            }
        }

        stage('Test') {
            steps {
                sh 'test -f app.py'
                sh 'test -f Dockerfile'
                sh 'test -f requirements.txt'
                sh "grep -q 'Flask Docker CI/CD Project is Running' app.py"
                echo 'All basic checks passed!'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t flask-docker-cicd .'
            }
        }
    }
}
