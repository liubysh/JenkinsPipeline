pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building the .NETCore app'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing the app'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy the app to the server'
      }
    }

  }
  
}