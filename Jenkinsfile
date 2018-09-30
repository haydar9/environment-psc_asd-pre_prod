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
      when {
        branch 'master'
        branch 'release/*'
      }
      input {
        message 'Should we continue?'
        id 'Yes, we should.'
        submitter 'alice,bob,admin'
        parameters {
          string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        }
      }
      steps {
        sh 'echo "Publishing to artifact"'
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
