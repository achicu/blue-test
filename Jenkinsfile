#!/usr/bin/env groovy

import groovy.json.JsonSlurper

def readPackageJson(String file) {
  def contents = readFile(file)
  def pkgJson = new JsonSlurper().parseText(contents)
  echo pkgJson
}

pipeline {
  agent any
  stages {
    stage('Setting up the pipeline') {
      steps {
        readPackageJson('package.json')
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
