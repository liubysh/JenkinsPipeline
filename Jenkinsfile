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
          environment{
            LocalVariable = "HelloLocal"
          }
          steps {
            writeFile(file: 'LogTestFile.txt', text: "This is automation log file with environment variable ${ChromeDriverPath} and local var ${LocalVariable}")
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploy the app to the server'
          }
        }

        stage('error') {
          steps {
            archiveArtifacts 'LogTestFile.txt'
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Driver\\Path\\ChromeDriver.exe'
  }
}