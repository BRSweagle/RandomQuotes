pipeline {
  agent any
  stages {
    stage('ConfigUpload') {
      steps {
        SWEAGLEUpload(actionName: 'UploadConfig', fileLocation: '/Users/boondock/Documents/GitHub/RandomQuotes', format: 'json', nodePath: 'Eldorado', allowDelete: true, filenameNodes: true, subDirectories: true, withSnapshot: true, tag: '${BUILD_ID}')
      }
    }

  }
}