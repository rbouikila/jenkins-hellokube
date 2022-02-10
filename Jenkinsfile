pipeline {

  agent {
    label 'kube-slave'
  }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/rbouikila/jenkins-hellokube.git', branch:'main'
      }
    }
  }
}
