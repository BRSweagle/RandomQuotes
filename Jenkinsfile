pipeline {
  agent any
  stages {
    stage('ConfigUpload') {
      steps {
        SWEAGLEUpload(actionName: 'UploadConfig', fileLocation: 'https://github.com/BRSweagle/RandomQuotes', format: 'json', nodePath: '/Users/boondock/.jenkins/workspace/Random Quotes', allowDelete: true, filenameNodes: true, subDirectories: true, withSnapshot: true, tag: '${BUILD_ID}')
      }
    }

  }
}