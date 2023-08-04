pipeline {
  agent any
  tools {
    maven 'maven'
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
  stage ('Deploy') {
    steps {
        sh 'ssh ec2-user@ec2-52-47-100-247.eu-west-3.compute.amazonaws.com'
        sh 'ls'
      }
    }
  }
}
