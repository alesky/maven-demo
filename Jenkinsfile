pipeline {
  agent any
  stages {
    stage('scan') {
      parallel {
        stage('scan') {
          steps {
            withSonarQubeEnv 'scanner'
          }
        }

        stage('') {
          steps {
            echo '${env.BUILD_NUMBER}'
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