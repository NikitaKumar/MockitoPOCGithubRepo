pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        parallel(
          "Compile": {
            bat 'mvn clean compile'
            
          },
          "Package": {
            bat 'mvn package'
            
          }
        )
      }
    }
    stage('SCA') {
      steps {
        bat 'sonar-scanner'
      }
    }
  }
}