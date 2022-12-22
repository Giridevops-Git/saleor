pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'saleor-brc', url: 'https://github.com/Giridevops-Git/saleor.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t girishg/saleor:QA'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push girishg/saleor:QA'
            }
        }
    }
}