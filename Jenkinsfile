pipeline {
    agent any
    stages {
        stage('run'){
            steps {
                python hello.py
            }
        }
    }
    post {
        always {
            emailext body: 'A Test EMail', subject: 'Test', to: 'ataberk.ozek@ayrotek.com.tr'
        }
    }
}