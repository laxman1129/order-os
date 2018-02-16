pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh './mvnw clean '
      }
    }
    stage('install') {
      steps {
        sh '''./mvnw install
./mvnw sonarqube
./mvnw package'''
      }
    }
    stage('deploy') {
      steps {
        sh './mvnw deploy'
      }
    }
  }
}