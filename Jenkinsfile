pipeline{
    agent any

    stages{
        stage('Clonar o repositório, instalar dependências!'){
            steps{
                git branch: 'main', url: 'https://github.com/alexgrocha/automacao_UI_cypress.git'
                sh 'npm install'
            }
        }
        stage('Abrir Servidor'){
            steps{
                sh 'NO_COLOR=1 npm run cy:run | true'
                sh 'npm run cy:report'
            }
        }
        stage('Report'){
            steps {
                publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'mochawesome-report', reportFiles: 'report.html', reportName: 'Teste Aula Cypress parte II - atividade 11', reportTitles: '', useWrapperFileDirectly: true])
            }
        }
    }    
}