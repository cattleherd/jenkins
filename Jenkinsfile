pipeline {
  agent any

  stages {
    stage('Repro Groovy Stringification') {
      steps {
        // Parse the JSON
        script {
          def unitTestData = readJSON file: 'unittest-report.json'
          // This will print only the first entry, e.g. "[numFailedTestSuites:1]"
          echo "unitTestData: ${unitTestData}"
        }
      }
    }
  }
}
