pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/prabhgill02/Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the Python application...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'pytest || true'
            }
        }

        stage('Notify') {
            steps {
                mail to: 'prabhdeepsinghgill1@gmail.com',
                     subject: 'Jenkins Build Notification',
                     body: "The Jenkins build has completed. Check Jenkins for details."
            }
        }
    }
}
