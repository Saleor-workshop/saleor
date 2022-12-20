pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/Saleor-workshop/saleor.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t aegonn/saleor:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push aegonn/saleor:DEV'
            }
        }
    }
}
