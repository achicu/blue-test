pipeline {
  agent any
  stages {
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