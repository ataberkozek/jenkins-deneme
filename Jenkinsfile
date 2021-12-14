pipeline {
    agent any
    stages {
        stage('check') {
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
            emailext body: "Build number: ${BUILD_NUMBER} has result ${currentBuild.currentResult}.", subject: "Status of pipeline: ${JOB_NAME}", to: "ataberk.ozek@ayrotek.com.tr"
        }
        failure {
            emailext attachLog: true, body: "Build number: ${BUILD_NUMBER} with build url: ${BUILD_URL} has result ${currentBuild.currentResult}.", subject: "Status of pipeline: ${JOB_NAME}", to: "ataberk.ozek@ayrotek.com.tr"
        }
        unstable {
            emailext attachLog: true, body: "Build number: ${BUILD_NUMBER} with build url: ${BUILD_URL} has result ${currentBuild.currentResult}.", subject: "Status of pipeline: ${JOB_NAME}", to: "ataberk.ozek@ayrotek.com.tr"
        }
    }
    }