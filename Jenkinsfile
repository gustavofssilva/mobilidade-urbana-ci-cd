pipeline {
    agent any
    tools {
        nodejs 'NodeJS'  // Nome da configuração de NodeJS criada nas configurações do Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                echo 'Fazendo o checkout do código...'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Iniciando etapa de Build...'
                bat 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Iniciando etapa de Testes...'
                bat 'npm test'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Iniciando Deploy para Staging...'
                bat 'deploy_staging.bat'
            }
        }
    }
    post {
        always {
            echo 'Limpando...'
        }
        success {
            echo 'Pipeline executada com sucesso!'
        }
        failure {
            echo 'Pipeline falhou. Verifique os erros!'
        }
    }
}
