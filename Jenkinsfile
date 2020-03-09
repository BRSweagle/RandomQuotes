pipeline {
  agent any
  stages {
    stage('ConfigUpload') {
      steps {
        SWEAGLEUpload(actionName: 'UploadConfig', fileLocation: 'https://github.com/BRSweagle/RandomQuotes.git', format: 'json', nodePath: 'Eldorado', allowDelete: true, filenameNodes: true, subDirectories: true, withSnapshot: true, tag: '${BUILD_ID}')
      }
    }

  }
}