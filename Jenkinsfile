pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/prabhgill02/Jenkins.git'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                script {
                    // Install pytest
                    powershell '''
                        python -m pip install
                        pip install pytest
                    '''
                }
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
                powershell 'pytest'
            }
        }
    }

    post {
        success {
            echo "Deployment successful!"
        }
        failure {
            echo "Deployment failed."
        }
    }    
}
