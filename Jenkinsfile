pipeline {
  agent any
  stages {
    stage('Git Chechout'){
       steps {
      git branch: 'main', url: 'https://github.com/paramesh416/demo-counter-app.git'
       }
    }
    stage('UNIT Testing'){
      steps{
        withMaven(maven: 'mvn') {
            sh "mvn test"
        }
      }
    }
  }
}


   

      
      
  
