pipeline {
  agent any
  stages {
    stage('Show Truncated Preview') {
      steps {
        script {
          def unitTestData = readJSON file: 'unittest-report.json'

          // This will invoke JSONObject.toString() and print the truncated preview
          echo 'unitTestData: ' + unitTestData.toString()
        }
      }
    }
  }
}
