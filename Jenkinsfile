pipeline {
  agent any
  environment {
    DOCKER_IMAGE_NAME = '124939912975.dkr.ecr.us-east-1.amazonaws.com/docker'
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
    stage('EcrLogin') {
      steps {
         sh 'aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 124939912975.dkr.ecr.us-east-1.amazonaws.com'
      }
    }
  }
}
