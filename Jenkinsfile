pipeline {
  agent any
  stages {
    stage ('Initialize') {
        steps {
            script {
                def v = checkout scm
                env.GIT_COMMIT = v.GIT_COMMIT
                env.GIT_PREVIOUS_SUCCESSFUL_COMMIT = v.GIT_PREVIOUS_SUCCESSFUL_COMMIT
            }
        }
    }

    stage ('Trigger subproject build') {
        steps {
            script {
                def v = sh(returnStatus:true, script: "git diff --name-only $GIT_PREVIOUS_SUCCESSFUL_COMMIT")
            }
        }
    }
  }
}
