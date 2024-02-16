pipeline {
  agent {
    image 'manoj:v2.0'
  }
  
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
