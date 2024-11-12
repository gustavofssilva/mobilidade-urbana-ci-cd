pipeline {
    agent any  // Seleciona qualquer nó disponível
    tools {
        nodejs 'NodeJS'  // Certifique-se de que o NodeJS está instalado e configurado em "Gerenciar Jenkins"
    }
    stages {
        stage('Checkout') {
            steps {
                echo 'Fazendo o checkout do código...'
                checkout scm  // Obtém o código do repositório configurado
            }
        }
        stage('Build') {
            steps {
                echo 'Iniciando etapa de Build...'
                bat 'npm install'  // Instala dependências usando o npm no Windows
            }
        }
        stage('Test') {
            steps {
                echo 'Iniciando etapa de Testes...'
                bat 'npm test'  // Roda os testes do projeto
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Iniciando Deploy para Staging...'
                // Execute seu comando de deploy. Pode ser um script .bat específico para Windows:
                bat 'deploy_staging.bat'  // Crie este arquivo .bat para gerenciar o deploy
            }
        }
    }
    post {
        always {
            echo 'Limpando...'
            // Qualquer ação de limpeza pós-pipeline, como excluir arquivos temporários, se necessário.
        }
        success {
            echo 'Pipeline executada com sucesso!'
        }
        failure {
            echo 'Pipeline falhou. Verifique os erros!'
        }
    }
}
