pipeline {
  agent any
  tools {
    maven 'maven'
  }
   environment {
    DOCKERHUB_CREDENTIALS = credentials('DOCKERHUB')
  }
    
  stages {
    stage ('test jar') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage('Build') {
      steps {
        sh 'id'
        sh 'docker build -t nedaljed/lab1springboot .'
      }
    }
    stage('Login') {
      steps {
        sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
      }
    }
    stage('Push') {
      steps {
        sh 'docker push nedaljed/lab1springboot'
      }
        }
      }
  }
