pipeline {
  agent {
    label "maven"
  }

  environment {
  }

  stages {
    stage("CI Build and push snapshot") {
        when {
            branch "PR-*"
        }

        steps {
            sh "mvn clean test package"
        }
    }

    stage("Build and Push Release") {
        when {
            branch "master"
        }
        steps {
            sh "mvn clean deploy"
        }

    }
  }
}
