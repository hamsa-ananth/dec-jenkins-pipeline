pipeline{
    agent any
     
    environment {
        CURRENT_ENV = 'prod'
    }
    

    parameters {
        booleanParam(name: 'DEPLOY', description:'DEPLOY APP')
    }
    
    
    stages{

        stage('CHECKOUT') {
            steps {
                checkout ([$class : 'GitSCM',
                branches: [[name: '*/main']],
                extensions: [],
                userRemoteConfigs: [[credentialsId: 'Jenkins-demo-private', 
                url: 'https://github.com/hamsa-ananth/Jenkins-demo.git']]])
                
                sh '''
                    echo GIT_BRANCH : $GIT_BRANCH
                    echo BRANCH_NAME : $BRANCH_NAME
                    '''
                } 


            }
    
        stage('STAGE1 when branch') {
            when {
                expression{
                return env.GIT_BRANCH == 'origin/main'
            }
        }
            steps{
                 echo "this is stage 1 and current env is ${env.CURRENT_ENV}"
            sh '''
            pwd
            ls -lrt
            sleep 5
            '''
        }
    }
        stage(' stage2 when environment') {
            when{
                environment name: 'CURRENT_ENV', value: 'prod'
       }
            steps{
                echo "this is stage 2 and current env is ${env.CURRENT_ENV}"
                sh '''
                pwd
                ls -lrt
                sleep 5
            '''
            } 
    }
        stage('stage3 when parameter') {
            when {
                expression {params.DEPLOY == true}
           }
            steps{
                echo "this is stage 3 and current env is ${env.CURRENT_ENV}"
                sh 'sleep 5'
        }
    }
    }
}

    
            
    
    
