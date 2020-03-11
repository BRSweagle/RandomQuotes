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
        SWEAGLEUpload(actionName: 'Upload JSON Files', fileLocation: 'config.json', format: 'json', nodePath: 'Eldorado,releases,jenkinsConf,new', withSnapshot: true, subDirectories: true, description: 'Upload json files')
      }
    }

    stage('ValidateConfig') {
      steps {
        SWEAGLEValidate(actionName: 'NoHTTP', mdsName: 'jenkinsConf', errMax: 5)
      }
    }

  }
}