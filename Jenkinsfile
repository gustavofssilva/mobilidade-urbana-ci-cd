pipeline {
    agent any

    stages {
        stage('Build') {
            steps {             
                sh 'npm install'
                sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Deploy to Staging') {
            steps {
                
                sh './deploy_staging.sh'
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
            // sh 'rm -rf node_modules'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
