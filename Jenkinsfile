pipeline {
  agent any
  stages {
    stage('Git Chechout'){
       steps {
      git branch: 'main', url: 'https://github.com/paramesh416/demo-counter-app.git'
       }
    }
    stage('Unit test'){
      steps {
        withMaven(maven: 'maven_3_8_6') {
           sh 'mvn clean install'
          }
      }
      
      stage('Test Stage'){
        steps {
            withMaven(maven: 'maven_3_8_6') {
              sh 'mvn test'
                }
            }
        }
    }
  }
}


   

      
      
  
