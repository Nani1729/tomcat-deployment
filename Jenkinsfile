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
    stage('build') {
      steps {
        deploy adapters: [tomcat9(credentialsId: 'tomcat-9', path: '', url: 'http://54.175.202.133:8085')], contextPath: 'demo', war: '"**/*.war"'
      }
    }
  }
}
