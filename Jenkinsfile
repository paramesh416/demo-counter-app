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
     stage('Static Code Analysis'){
      steps{
        withSonarQubeEnv('credentailId: sonar-api')
        sh "mvn clean package sonar:sonar"
      }
     }
  }
}
   



   

      
      
  
