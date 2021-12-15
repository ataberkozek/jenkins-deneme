pipeline {
    agent any
    stages {
        stage('Run Tests') {
            stage('Backend Tests') {
                steps {
                    sh 'node ./backend/test.js'
                }
            }
        }
    post {
        success {
            emailext body: "Build number: ${BUILD_NUMBER} has result ${currentBuild.currentResult}.", subject: "Status of pipeline: ${JOB_NAME}", to: "ataberk.ozek@ayrotek.com.tr"
        }
        failure {
            emailext attachLog: true, body: "Build number: ${BUILD_NUMBER} with build url: ${BUILD_URL} has result ${currentBuild.currentResult}. Here are the failed tests: ${FAILED_TESTS}", subject: "Status of pipeline: ${JOB_NAME}", to: "ataberk.ozek@ayrotek.com.tr"
        }
        unstable {
            emailext attachLog: true, body: "Build number: ${BUILD_NUMBER} with build url: ${BUILD_URL} has result ${currentBuild.currentResult}.", subject: "Status of pipeline: ${JOB_NAME}", to: "ataberk.ozek@ayrotek.com.tr"
        }
    }
    }
}