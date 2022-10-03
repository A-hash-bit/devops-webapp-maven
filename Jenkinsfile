pipeline{
    agent any
    
    environment { 
        CC = 'clang'

        GIT_COMMIT_SHORT = sh(
                script: "printf \$(/opt/git/bin/git rev-parse --short ${GIT_COMMIT})",
                returnStdout: true
        )
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
            echo "${GIT_COMMIT}"
            echo "${GIT_COMMIT_SHORT}"
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
          
