pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Code is pulled from GitHub automatically'
                sh 'ls -la'
            }
        }

        stage('Install dependencies') {
            steps {
                sh '''
                    python3 -m venv .venv
                    . .venv/bin/activate
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                    . .venv/bin/activate
                    pytest -v --junitxml=test-results.xml
                '''
            }
        }
    }

    post {
        always {
            junit 'test-results.xml'
        }
        success {
            echo 'Pipeline passed'
        }
        failure {
            echo 'Pipeline failed: check the stage with the red X'
        }
    }
}
