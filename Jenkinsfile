pipeline {
    agent { docker { image 'python:3.10.1-alpine' } }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
            }
        }
        stage('run'){
            steps {
                python hello.py
            }
        }
    }
    post {
        success {
            emailext body: '${env.BUILD_URL} has result ${currentBuild.result}', subject: 'Status of pipeline: ${currentBuild.fullDisplayName}', to: 'ataberk.ozek@ayrotek.com.tr'
        }
        failure {
            emailext body: '${env.BUILD_URL} has result ${currentBuild.result}', subject: 'Status of pipeline: ${currentBuild.fullDisplayName}', to: 'ataberk.ozek@ayrotek.com.tr'
        }
}