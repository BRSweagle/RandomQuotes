pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        git(url: 'https://github.com/BRSweagle/RandomQuotes', poll: true)
        sleep 2
      }
    }

    stage('UploadConfig') {
      steps {
        SWEAGLEUpload(actionName: 'Upload JSON Files', fileLocation: 'config.json', format: 'json', nodePath: 'Eldorado,releases,release2.0', description: 'Upload json files', showResults: true, tag: 'Version:1.7.${BUILD_ID}', filenameNodes: true, withSnapshot: true)
      }
    }

  }
}