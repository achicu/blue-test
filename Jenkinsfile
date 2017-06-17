pipeline {
  agent any
  stages {
    stage('Check build') {
      steps {
        parallel(
          "Run on Windows": {
            node(label: 'macosx') {
              echo 'macosx'
            }
            
            
          },
          "Run on Mac": {
            node(label: 'windows') {
              echo 'windows'
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