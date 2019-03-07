pipeline {
  agent any
  stages {
    stage('Start') {
      steps {
        echo 'Starting pipeline'
      }
    }
    stage('checkout') {
      steps {
        git(url: 'https://github.com/arturopst/monorepo.git', branch: 'master')
      }
    }
  }
}