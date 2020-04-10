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
            echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
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