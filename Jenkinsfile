pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo "building..."'
        sh 'echo "build successful."'
      }
    }
    stage('Unit Tests') {
      when {
        branch 'master'
      }
      input {
        message 'Should we continue?'
        id 'Yes, we should.'
        submitter 'alice,bob'
        parameters {
          string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        }
      }
      steps {
        sh 'echo "Running unit tests..."'
        sh 'echo "Unit tests successfully run."'
      }
    }
    stage('Integration Tests') {
      steps {
        sh 'echo "Running integration tests..."'
        sh 'echo "Integration tests successfully run."'
      }
    }
    stage('Publish to Artifact') {
      steps {
        sh 'echo "Publishing to artifact"'
      }
    }
  }
  options {
    disableConcurrentBuilds()
  }
}