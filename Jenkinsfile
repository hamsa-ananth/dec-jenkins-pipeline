pipeline{
    agent any
    
    stages{
        stage('stage1'){
            steps {
                sh 'sleep 5'
                echo "This is stage 1"

            sh'''
            sleep 5
            echo "This is linux batch"
            '''
            }
        }
        stage('stage 2') {
            steps {
                batch '''
                #!/bin/bash
                pwd
                ls -lrt
                sleep 5
                '''
                echo "This is stage 2"
            }
        }
            }
        }
