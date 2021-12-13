pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'python --version'
            }
        }
        stage('run'){
            steps {
               sh 'python3 hello.py'
            }
        }
    }
    post {
        success {
            emailext body: ${BUILD_URL}' has result' ${currentBuild.result}, subject: 'Status of pipeline: '${currentBuild.fullDisplayName}, to: 'ataberk.ozek@ayrotek.com.tr'
        }
        failure {
            emailext body: ${BUILD_URL}' has result '${currentBuild.result}, subject: 'Status of pipeline: '${currentBuild.fullDisplayName}, to: 'ataberk.ozek@ayrotek.com.tr'
        }
    }
    }