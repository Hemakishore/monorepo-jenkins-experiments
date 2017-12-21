pipeline {
  agent any
  stages {
    stage ('Initialize') {
      steps {
        script {
            def v = checkout scm
            echo v.dump()
        }
      }
    }
  }
}
