pipeline {

  agent any
    stages{
      stage('Test Code With Sonarqube') {
        steps {
            sh "echo "INI LAGI TESTING APPS""
          }
        }
      }
      stage('Build with Docker') {
        steps {
          sh "echo "INI LAGI BUILD DOCKER IMAGE""
        }
      }
      stage('Publish Docker Image') {
        steps {
          sh "echo "INI LAGI PUSH DOCKER IMAGE""
        }
      }
      stage('Deploy to Kubernetes') {
        when {
           changelog 'deployment'
        }
        input {
          message "Should we continue?"
            ok "Yes, we should."
            parameters {
              string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who are you?')
            }
        }
        steps {
          script {
            sh "echo "DEPLOY APPS""
#            if ( env.GIT_BRANCH == "feature*" ) {
#              sh "echo "INI LAGI DEPLOY APPS KE SERVER DEV""
#            }
#            else if ( env.GIT_BRANCH == 'main' ) {
#              sh "echo "INI LAGI DEPLOY APPS KE SERVER PROD""
#            }
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
