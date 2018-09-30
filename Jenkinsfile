pipeline {
  options {
    disableConcurrentBuilds()
  }
  agent any
  stages {
    stage('Stage 1') {
      steps {
        sh 'echo "Stage 1"'
      }
    }
    stage('Stage 2') {
      when {
        branch 'master'
      }
      steps {
        sh 'echo "Stage 2'
      }
    }
  }
}
