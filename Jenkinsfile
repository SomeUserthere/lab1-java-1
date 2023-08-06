pipeline {
  agent any
  tools {
    maven 'maven'
  }
   environment {
    DOCKERHUB_CREDENTIALS = credentials('DOCKERHUB')
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t lab1-java-1/ .'
      }
    }
    stage('Login') {
      steps {
        sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
      }
    }
    stage('Push') {
      steps {
        sh 'docker push springboot-app/lab1-java-1'
      }
  }
}
