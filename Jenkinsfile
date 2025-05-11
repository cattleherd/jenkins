pipeline {
  agent any

  stages {
    stage('Generate Huge JSON') {
      steps {
        script {
          // Build a map with lots of keys so JSON-lib will truncate its toString()
          def big = [:]
          (1..50).each { i -> big["field${i}"] = "value${i}" }
          writeFile file: 'unittest-report.json',
                    text: groovy.json.JsonOutput.toJson(big)
        }
      }
    }

    stage('Reproduce Stringification Mishap') {
      steps {
        script {
          // Parse via Pipeline Utility Steps
          def unitTestData = readJSON file: 'unittest-report.json'

          // This will invoke JSONObject.toString(), which truncates
          echo "unitTestData: ${unitTestData}"
        }
      }
    }
  }
}
