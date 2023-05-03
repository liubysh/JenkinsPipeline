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
            echo "Get the DriverPath ${ChromeDriverPath}"
          }
        }

        stage('Test log') {
          steps {
            writeFile(file: 'LogTestFile.txt', text: 'This is automation log file')
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