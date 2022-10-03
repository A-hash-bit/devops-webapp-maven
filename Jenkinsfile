pipeline{
    agent any
    
    environment { 
        CC = 'clang'
    }
    
    stages{
        stage("Checkout"){
            steps{
                echo "========executing checkout========"
                git url:"https://github.com/A-hash-bit/spring-petclinic.git", branch:"main"
            }
        }
        stage("Env Variables"){
            steps{
            echo "${env.BUILD_ID}"
            echo "${branch_name}"
            }
        }    
        stage('Example') {
            environment { 
                DEBUG_FLAGS = '-g'
            }
            steps {
                sh 'printenv'
            }
        }
        
        
    }
}
          
