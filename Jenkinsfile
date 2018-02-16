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
        sh './mvnw install'
      }
    }
    stage('sonarqube') {
      steps {
        sh './mvnw sonarqube'
      }
    }
    stage('package') {
      steps {
        sh './mvnw package'
      }
    }
    stage('confirm') {
      steps {
        echo 'do you want to deploy'
      }
    }
    stage('deploy') {
      steps {
        sh './mvnw deploy'
      }
    }
  }
}