pipeline {
  agent any
  environment {
    PATH = "/opt/maven/bin:$PATH"
  }
  stages {
    stage('Git Chechout'){
       steps {
      git branch: 'main', url: 'https://github.com/paramesh416/demo-counter-app.git'
       }
    }
    stage('UNIT Test'){
      steps{
        sh "mvn test"
      }
    }
     stage('Maven Build'){
      steps{
        sh "mvn clean install"
      }
    }
    stage('Integration Testing') {
      steps{
          sh "mvn verify -DskipUnittests"
      }
    }
   stage("build & SonarQube analysis") {
     environment {
       scannerHome = tool 'SonarQubeScanner'
     }
     steps {
       withSonarQubeEnv('sonarqube') {
         sh "${scannerHome}/bin/sonar-scanner"
       }
     }
   }
    stage('Quality Gate Status'){
      steps{
        scrpit{
          
          waitforQualityGate abortPipeline: false, credentialsId: 'sonar-api'
        }
      }
    }
  }
}
              
            
     
        
       
  
   



   

      
      
  
