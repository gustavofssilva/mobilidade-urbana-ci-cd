pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Exemplo: Se fosse uma aplicação Node.js
                // sh 'npm install'
                // sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Exemplo: Rodar testes de unidade
                // sh 'npm test'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
                // Exemplo: Enviar arquivos para o servidor de homologação
                // sh './deploy_staging.sh'
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
