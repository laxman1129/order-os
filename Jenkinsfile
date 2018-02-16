pipeline {
  agent {
    node {
      label 'maven'
    }
    
  }
  stages {
    stage('build') {
      steps {
        sh 'mvn fabric8:build'
      }
    }
  }
  environment {
    maven = 'maven'
  }
}