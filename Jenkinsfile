pipeline {
  agent any
  stages {
    stage('Verify Map Contents') {
      steps {
        script {
          // 1) Read via Pipeline Utility (gives you JSONObject)
          def jsonObj = readJSON file: 'unittest-report.json'

          // 2) Read raw text + parse via JsonSlurper (gives you LinkedHashMap)
          def text    = readFile('unittest-report.json')
          def asMap   = new groovy.json.JsonSlurper().parseText(text)

          // 3) Show how each prints
          echo "---- JSONObject.toString() preview ----"
          echo jsonObj.toString()                

          echo "---- LinkedHashMap.toString() preview ----"
          echo asMap.toString()                 

          // 4) Show the actual number of keys and list them
          echo "Map has ${asMap.size()} top-level keys"
          echo "Keys: ${asMap.keySet()}"
        }
      }
    }
  }
}
