pipeline {
  agent any
  stages {
    stage('Setting up the pipeline') {
      def pkgJson = new JsonSlurper().parseText(new File('package.json').getText('UTF-8'))
      echo pkgJson
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
