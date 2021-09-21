pipeline {
  agent {
    node {
      label 'agent1'
    }

  }
  stages {
    stage('Clone') {
      steps {
        git(url: 'https://github.com/daviesadrian/devops-webapp1-1', branch: 'master')
      }
    }

    stage('Build') {
      steps {
        sh '''whoami
date
echo $PATH
ls -la
./gradlew build --info'''
      }
    }

    stage('Publish') {
      steps {
        archiveArtifacts(artifacts: 'build/libs/*.war', fingerprint: true, onlyIfSuccessful: true)
      }
    }

  }
}