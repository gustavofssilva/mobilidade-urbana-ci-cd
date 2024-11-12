pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Fazendo o checkout do código...'
                checkout scm
            }
        }
        stage('Instalar Dependências') {
            steps {
                echo 'Instalando dependências com Yarn...'
                // Altere `sh` para `bat`
                bat 'yarn install'
            }
        }
        stage('Build') {
            steps {
                echo 'Iniciando etapa de Build com Yarn...'
                bat 'yarn build'
            }
        }
        stage('Test') {
            steps {
                echo 'Iniciando etapa de Testes com Yarn...'
                bat 'yarn test'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Iniciando Deploy para Staging...'
                bat 'deploy_staging.bat' // Use um script .bat no lugar de .sh se necessário
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
