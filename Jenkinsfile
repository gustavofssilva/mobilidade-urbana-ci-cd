pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                // Coloque aqui o comando para compilar o projeto
                // Por exemplo, para Node.js, use 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing the project...'
                // Coloque aqui o comando para rodar os testes
                // Por exemplo, para Node.js, use 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the project...'
                // Coloque aqui o comando para implantar o projeto
                // Exemplo: copiar arquivos para um servidor de homologação
            }
        }
    }
}
