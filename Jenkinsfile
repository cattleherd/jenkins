pipeline {
  agent any
  stages {
    stage('Debug JSON') {
      steps {
        // Read in your file
        script {
          def data = readJSON file: 'unittest-report.json'

          // 1️⃣ Show the class
          echo "Data class: ${data.getClass()}"

          // 2️⃣ Access key fields
          echo "Total tests        : ${data.numTotalTests}"
          echo "Failed test suites : ${data.numFailedTestSuites}"

          // 3️⃣ Show all top-level keys (if you need to see what’s in there)
          echo "All keys: ${data.keySet()}"
        }
      }
    }
  }
}
