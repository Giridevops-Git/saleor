pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/Giridevops-Git/saleor.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t girishg/saleor:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push girishg/saleor:DEV'
            }
        }
    }
}