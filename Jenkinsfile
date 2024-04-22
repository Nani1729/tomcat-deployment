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
    stage('Deploy') {
      steps {
        deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://54.87.126.193:8888/')], contextPath: 'demo', war: '**/*.war'
      }
    }
  }
}
