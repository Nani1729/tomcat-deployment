pipeline {
  agent any
  stages {
    stage('java') {
      steps {
        sh 'java -version'
      }
    }
    stage('clean') {
      steps {
        sh 'mvn clean'
      }
    }
    stage('build') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
