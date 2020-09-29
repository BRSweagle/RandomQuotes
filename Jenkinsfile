pipeline {
  agent any
  stages {
    stage('Retrieve Sources') {
      steps {
        git(url: 'https://github.com/BRSweagle/RandomQuotes', poll: true)
        sleep 2
      }
    }

    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            git(poll: true, url: 'https://github.com/BRSweagle/RandomQuotes')
          }
        }

        stage('UploadConfig') {
          steps {
            SWEAGLEUpload(actionName: 'UploadConfig', fileLocation: '*.json', format: 'json', nodePath: 'Icarus,Components,Jenkins', autoRecognize: true, filenameNodes: true, tag: '${BUILD_ID}')
          }
        }

      }
    }

    stage('Testing') {
      parallel {
        stage('Testing') {
          steps {
            echo 'TestingStep'
          }
        }

        stage('ValidateConfig') {
          steps {
            SWEAGLEValidate(actionName: 'Validate', mdsName: 'Icarus.Dev-1', noPending: true)
          }
        }

        stage('SnapshotConfig') {
          steps {
            SWEAGLESnapshot(mdsName: 'Icarus.Dev-1', actionName: 'Snapshot Config', tag: '${BUILD_ID}')
          }
        }

      }
    }

    stage('Deploy to QA') {
      steps {
        SWEAGLEExport(actionName: 'Deploy Snapshot', mdsName: 'Icarus.Dev-1', exporter: 'all', format: 'json')
      }
    }

    stage('QA Tests') {
      steps {
        echo 'QA Tests'
      }
    }

    stage('SNOW DevOps') {
      steps {
        echo 'Data sent to SNOW CAB'
      }
    }

    stage('Depoy to PROD') {
      steps {
        echo 'Deployed'
      }
    }

  }
}