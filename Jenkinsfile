pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        git(url: 'https://github.com/BRSweagle/RandomQuotes', poll: true)
        sleep 2
      }
    }
  }
}
