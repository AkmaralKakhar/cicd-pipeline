pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh './scripts/build.sh'
      }
    }

    stage('test') {
      steps {
        sh './scripts/test.sh'
      }
    }

    stage('dockerize') {
      steps {
        sh 'docker build -t akmaral2002/ci-cd-epam .'
      }
    }

    stage('docker-push') {
      steps {
        sh 'docker push akmaral2002/ci-cd-epam'
      }
    }

  }
}