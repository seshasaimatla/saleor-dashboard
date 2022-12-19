pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/seshasaimatla/saleor-dashboard.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t matlaseshasai28/saleor-dashboarb:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push matlaseshasai28/saleor-dashboarb:DEV'
            }
        }
    }
}
