pipeline {
  agent any
  stages {
    stage('Check build') {
      steps {
        parallel(
          "Run on macos": {
            node(label: 'macos') {
              echo 'macos'
            }
            
            
          },
          "Run on windows": {
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