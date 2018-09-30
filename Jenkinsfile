pipeline {
  options {
    disableConcurrentBuilds()
  }
  agent {
    label "jenkins-jenkins-slave"
  }
  stages {
    stage('Stage 1') {
      steps {
        sh 'echo "Stage 1"'
      }
    }
    stage('Stage 2') {
      input {
message "Should we continue?"
ok "Yes, we should."
submitter "alice,bob"
parameters {
string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
}
}
      when {
        branch 'master'
      }
      steps {
        sh 'echo "Stage 2'
      }
    }
  }
}
