pipeline {
  agent any
  stages {
    stage('Check build') {
      steps {
        parallel(
          "Run on Windows": {
            node(label: 'macos') {
              echo 'macos'
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