pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        git(url: 'https://github.com/BRSweagle/RandomQuotes', poll: true)
        sleep 2
      }
    }
    
        stage('UploadConfig'){

            steps {

                SWEAGLEUpload(
                actionName: 'Upload JSON Files',
                fileLocation: "*.json",
                format: 'json',
                markFailed: false,
                nodePath: 'Eldorado,releases,jenkinsConf',
                onlyParent: false,
                showResults: false,
                withSnapshot: false,
                subDirectories: true,
                description: 'Upload json files',
                tag: '',
                autoRecognize: false,
                allowDelete: false)

            }
        }
  }
}
