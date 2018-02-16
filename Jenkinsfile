pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn fabric8:build'
      }
    }
  }
}