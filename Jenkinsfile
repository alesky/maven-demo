pipeline {
  agent any
  stages {
    stage('scan') {
      parallel {
        stage('scan') {
          steps {
            withSonarQubeEnv 'sonar'
          }
        }

        stage('error') {
          steps {
            sh 'echo \'${env.BUILD_NUMBER}\''
          }
        }

      }
    }

    stage('build') {
      steps {
        sh 'mvn build'
      }
    }

  }
}