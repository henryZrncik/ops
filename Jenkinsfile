pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo "Checked out commit: ${env.GIT_COMMIT}"
            }
        }
        stage('Test') {
            steps {
                sh 'mvn clean test'
            }
        }
    }
    post {
        success {
            echo "✅ Tests passed!"
        }
        failure {
            echo "❌ Tests failed. See logs."
        }
    }
}