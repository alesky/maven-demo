pipeline {
  agent any
  stages {
    stage('scan') {
      steps {
        withSonarQubeEnv 'scanner'
      }
    }

    stage('build') {
      steps {
        sh 'mvn build'
      }
    }

  }
}