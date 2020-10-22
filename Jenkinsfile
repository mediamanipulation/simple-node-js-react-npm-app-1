pipeline {
  agent any
  stages {
    stage('') {
      agent {
        docker {
          image 'node:6-alpine'
          args '-p 3000:3000'
        }

      }
      environment {
        CI = 'true'
      }
      steps {
        sh '\'npm install\''
        sh '\'./jenkins/scripts/test.sh\''
        sh '''\'./jenkins/scripts/deliver.sh\'
                input message: \'Finished using the web Site? (Click "Proceed" to continue)\'
   \'./jenkins/scripts/kill.sh\''''
      }
    }

  }
}