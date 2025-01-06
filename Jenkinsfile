pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'sh \'./scripts/build.sh\''
      }
    }

    stage('test') {
      steps {
        sh 'sh \'./scripts/test.sh\''
      }
    }

    stage('dockerize') {
      steps {
        sh 'sh \'docker build -t akmaral2002/ci-cd-epam .\''
      }
    }

    stage('') {
      steps {
        sh '''# Docker login using Jenkins credentials (docker_hub_creds)
echo $DOCKER_PASSWORD | docker login -u $DOCKER_USERNAME --password-stdin
docker push akmaral2002/ci-cd-epam'''
      }
    }

  }
}