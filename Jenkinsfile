pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn fabric8:build'
      }
    }
    stage('Deploy and Test') {
      steps {
        sh 'mvn fabric8:deploy'
      }
    }
    stage('promote to qa') {
      steps {
        sh 'oc tag myproject/orders:latest myproject/orders:promoteToQA'
      }
    }
  }
}