pipeline{
    agent any
    tools{
       maven "Maven-3"
    }
    stages{
        stage("Checkout"){
            steps{
                 git 'https://github.com/A-hash-bit/devops-webapp-maven.git'
            }
        } 
        stage("Unit Test"){
            steps{
             sh "mvn test"
            }
        }
        stage("Sonar Analysis"){
            steps{
                withSonarQubeEnv("SonarQubeScaner-4.7.0") {
                println ${env.SONAR_HOST_URL} 
                sh "sonar:sonar"
                }
            }
        }
    }
}
          
