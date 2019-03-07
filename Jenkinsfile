pipeline {
  agent any
  stages {
    stage('Start') {
      steps {
        echo 'Starting pipeline'
      }
    }
    stage('checkout master') {
      parallel {
        stage('checkout') {
          steps {
            git(url: 'https://github.com/arturopst/monorepo.git', branch: 'master')
          }
        }
        stage('checkout develop') {
          steps {
            git(url: 'https://github.com/arturopst/monorepo.git', branch: 'develop')
          }
        }
      }
    }
    stage('build') {
      steps {
        dir(path: 'rest2') {
          sh './mvnw clean install'
        }

      }
    }
    stage('test') {
      steps {
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
  }
}