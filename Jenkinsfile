pipeline {

  agent any
    stages{
      stage('Test Code With Sonarqube') {
        steps {
          script {
            sh "echo INI LAGI TESTING APPS"
          }
        }
      }
      stage('Build with Docker') {
        steps {
          script {
            sh "echo INI LAGI BUILD DOCKER IMAGE"
          }
        }
      }
      stage('Publish Docker Image') {
        steps {
          script {
            sh "echo INI LAGI PUSH DOCKER IMAGE"
            sh "env"
          }
        }
      }
      stage('Deploy to Kubernetes') {
        steps {
          script {
            sh "echo DEPLOY APPS"
            if ( env.GIT_BRANCH == "origin/dev" ) {
              echo "INI LAGI DEPLOY APPS KE SERVER DEV"
            }
            else if ( env.GIT_BRANCH == 'origin/main' ) {
              echo "INI LAGI DEPLOY APPS KE SERVER PROD"
            }
          }
        }
      }
   }
    post {
        always {
            echo 'One way or another, I have finished'
        }
        success {
            echo 'I succeeded!'
        }
        failure {
            echo 'I failed :('
        }
    }
}
