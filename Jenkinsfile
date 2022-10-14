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
    stage('UNIT Testing') {
      steps{
        sh 'mvn test'
      }
    }
  }
}
   



   

      
      
  
