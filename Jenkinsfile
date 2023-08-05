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
         sshagent(credentials: ['SSH-DOCKER']) {
            sh '''
                ssh ec2-user@ec2-35-181-1-250.eu-west-3.compute.amazonaws.com 'docker ps'
            '''
          }
      }
    }
  }
}
