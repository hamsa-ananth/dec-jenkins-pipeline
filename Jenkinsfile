pipeline{
    agent none

    stages {
        stage('stage1'){
            agent { label 'slave1'}
            steps {
                sh '''
                sleep 5
                echo "This is stage 1"
                '''
            }
        }
        
        stage('build') {
            agent { label 'slave2'}
            steps {
                sh '''
                #!/bin/bash
                pwd
                ls -lrt
                sleep 5
                echo "This is stage 2"
                '''
            }
        }
    }
}
