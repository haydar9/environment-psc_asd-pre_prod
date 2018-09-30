pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo "building..."'
        sh 'echo "build successful."'
      }
    }
    stage('Test') {
      steps {
        parallel(
          'Unit Tests': {
            sh 'echo "Running unit tests..."'
            sh 'echo "Unit tests successfully run."'
          },
          'Integration Tests': {
            sh 'echo "Running integration tests..."'
            sh 'echo "Integration tests successfully run."'
          }
        )
      }
    }
    stage('Publish SNAPSHOT to Artifact') {
      when {
        branch 'dev'
      }
      steps {
        sh 'echo "Publishing to artifact"'
      }
    }
    stage('Publish RC to Artifact') {
      when {
        branch 'release/*'
      }
      steps {
        sh 'echo "Publishing to artifact"'
      }
    }
    stage('Publish RELEASE to Artifact') {
      when {
        branch 'master'
      }
      steps {
        sh 'echo "Publishing to artifact"'
      }
    }
  }
  options {
    disableConcurrentBuilds()
  }
}
