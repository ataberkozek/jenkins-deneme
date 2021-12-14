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
            emailext body: 'Build number: '$BUILD_NUMBER  ' has result ' $BUILD_STATUS, subject: 'Status of pipeline: '$PROJECT_NAME, to: 'ataberk.ozek@ayrotek.com.tr'
        }
        failure {
            emailext body: 'Build number: '$BUILD_NUMBER 'with build url: ' $BUILD_URL' has result' $BUILD_STATUS, subject: 'Status of pipeline: '$PROJECT_NAME, to: 'ataberk.ozek@ayrotek.com.tr'
        }
    }
    }