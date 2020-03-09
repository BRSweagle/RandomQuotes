pipeline {
  agent any
  stages {
      {
    stage('build') {
      steps {
        git(url: 'https://github.com/BRSweagle/RandomQuotes', poll: true)
        sleep 2
      }
      
    stage('ConfigUpload') {
      steps {
        SWEAGLEUpload(actionName: 'UploadConfig', fileLocation: 'https://github.com/BRSweagle/RandomQuotes.git', format: 'json', nodePath: 'Eldorado', allowDelete: true, filenameNodes: true, subDirectories: true, withSnapshot: true, tag: '${BUILD_ID}')
     }
    }
   }
  }
}
