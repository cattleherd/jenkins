pipeline {
  agent any
  stages {
    stage('Verify Map Contents') {
      steps {
        script {
          // 1) Read & parse as before
          def text  = readFile('unittest-report.json')
          def asMap = new groovy.json.JsonSlurper().parseText(text)

          // 2) Add 100 dummy keys to blow past Jenkins's line‐length cutoff
          (1..100).each { i ->
            // each value is a 50-character string
            asMap["dummyKey${i}"] = "x".multiply(50)
          }

          // 3) Echo the monster map in one go
          //    Jenkins will truncate the line somewhere after ~1 KB
          echo asMap.toString()
        }
      }
    }
  }
}
