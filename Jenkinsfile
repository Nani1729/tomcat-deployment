pipeline {
  agent any
  environment {
    DOCKER_IMAGE_NAME = 'manojreddy12/newrepo'
    DOCKER_VERSION = 'v2.0'
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
    stage('DockerBuild') {
      steps {
        sh 'docker build -t $DOCKER_IMAGE_NAME:$DOCKER_VERSION .'
      }
    }
    stage('DockerPush') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'docker-hub', passwordVariable: 'swaroop', usernameVariable: 'manoj')]) {
    sh 'docker login --username $manoj --password $swaroop'
          sh 'docker push $DOCKER_IMAGE_NAME:$DOCKER_VERSION'
}
         
      }
    }
  }
}
