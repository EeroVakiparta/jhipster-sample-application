pipeline {
  agent any
  stages {
    stage('sonar-docker') {
      steps {
        sh 'docker-compose -f src/main/docker/sonar.yml up -d'
      }
    }

    stage('sonar') {
      steps {
        sh './mvnw -Pprod clean verify sonar:sonar'
      }
    }

    stage('docker-verify') {
      steps {
        sh './mvnw -Pprod verify jib:dockerBuild'
      }
    }

    stage('docker up') {
      steps {
        sh 'docker-compose -f src/main/docker/app.yml up -d'
      }
    }

  }
}