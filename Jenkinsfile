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

        stage('Run Application') {
            steps {
                script {
                    // Run the Python app (app.py)
                    echo "Running the Python application..."
                    powershell script: '''
                    python app.py
                    '''
                }
            }
        }

         stage('Notify') {
            steps {
                script {
                    // Send notifications based on the result of the pipeline
                    if (true) {
                        echo "Build succeeded!"
                    } else {
                        echo "Build failed!"
                    }
                }
            }
        }               
    }    
}
