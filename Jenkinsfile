pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh './mvnw clean '
      }
    }
    stage('install') {
      parallel {
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
      }
    }
    stage('deploy') {
      steps {
        sh './mvnw deploy'
      }
    }
  }
}