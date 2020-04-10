pipeline {
  agent any
  stages {
    stage('scan') {
      parallel {
        stage('scan') {
          steps {
            withSonarQubeEnv('sonar') {
              sh 'mvn -X clean package sonar:sonar'
            }

          }
        }

        stage('error') {
          steps {
            sh 'echo $env.BUILD_NUMBER'
          }
        }

      }
    }

    stage('build') {
      steps {
        sh 'mvn package -X'
      }
    }

  }
}