pipeline{
    agent any
    
    stage{
        stage('stage1'){
            steps {
                batch 'sleep 5'
                echo "This is stage 1"

            batch '''
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