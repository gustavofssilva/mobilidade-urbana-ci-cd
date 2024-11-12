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
                sh 'yarn install'
            }
        }
        stage('Build') {
            steps {
                echo 'Iniciando etapa de Build com Yarn...'
                sh 'yarn build'
            }
        }
        stage('Test') {
            steps {
                echo 'Iniciando etapa de Testes com Yarn...'
                sh 'yarn test'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Iniciando Deploy para Staging...'
                sh './deploy_staging.sh'
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
