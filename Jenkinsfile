pipeline{
    agent { label 'slave1'}

    stages {
        stage('stage1'){
            steps {
                sh '''
                sleep 5
                echo "This is stage 1"
                '''
            }
        }
        
        stage('stage 2') {
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
