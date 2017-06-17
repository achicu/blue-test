import groovy.json.JsonSlurper

pipeline {
  agent any
  stages {
    stage('Setting up the pipeline') {
      steps {
        def contents = readFileFromWorkspace('package.json')
        def pkgJson = new JsonSlurper().parseText(contents)
        echo pkgJson
      }
    }
    stage('Check build') {
      steps {
        parallel(
          "Run on macos": {
            node(label: 'macos') {
              echo 'macos'
              sh '''echo `pwd`
ls -la'''
            }
            
            
          },
          "Run on windows": {
            node(label: 'windows') {
              echo 'windows'
              powershell 'dir'
            }
            
            
          }
        )
      }
    }
    stage('Done') {
      steps {
        echo 'Done'
      }
    }
  }
}
