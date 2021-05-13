pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        sh '''./mvnw verify
'''
      }
    }

    stage('end') {
      steps {
        echo 'hello'
      }
    }

  }
}