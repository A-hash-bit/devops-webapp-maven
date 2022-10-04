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
                withSonarQubeEnv("sonarQube-9.6.1") {
               // println ${env.SONAR_HOST_URL} 
                sh "sonar:sonar"
                }
            }
        }
    }
}
          
