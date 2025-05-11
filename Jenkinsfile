pipeline {
  agent any
  stages {
    stage('Prep') {
      steps {
        // Create a sample JSON so readJSON can find it
        writeFile file: 'unittest-report.json', text: '''{
          "numTotalTests": 3,
          "numFailedTestSuites": 1,
          "testResults": []
        }'''
      }
    }
    stage('Debug JSON') {
      steps {
        script {
          def unitTestData = readJSON file: 'unittest-report.json'
          echo "unitTestData class: ${unitTestData.getClass()}"
          echo "numTotalTests: ${unitTestData.numTotalTests}"
          // …etc…
        }
      }
    }
  }
}
