pipeline {
  agent any
  stages {
    stage('Development Build') {
      steps {
        echo ' Pull the code from Git hub repo'
        echo 'Create a Build using Repository'
      }
    }

    stage('Smoke Test') {
      steps {
        echo 'Run 2 Smoke Test'
      }
    }

    stage('Deploy in QA') {
      steps {
        echo 'Stop the Server'
        echo 'Move the build in QA'
        echo 'Start the Server in QA'
        echo 'Notify to QA by Email'
      }
    }

    stage('Integration Test') {
      parallel {
        stage('Integration Test') {
          steps {
            echo 'Sanity Test (UI)'
          }
        }

        stage('API Test') {
          steps {
            echo 'Run REST Automation Tests'
          }
        }

        stage('Performance Testing') {
          steps {
            echo 'Run Jmeter tests'
          }
        }

      }
    }

    stage('Certify') {
      steps {
        echo 'QA team Cerfity'
      }
    }

  }
}