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
        withSonarQubeEnv('My SonarQube Server') {
      // requires SonarQube Scanner for Maven 3.2+
      //sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
        sh './mvnw sonarqube'  
    }
        
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
