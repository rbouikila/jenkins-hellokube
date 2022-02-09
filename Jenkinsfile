pipeline {

  agent {
    kubernetes {
      yamlFile 'builder.yaml'
    }
  }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/rbouikila/jenkins-hellokube.git', branch:'main'
      }
    }

    stage('Kaniko Build & Push Image') {
      steps {
        container('kaniko') {
          script {
            sh '''
            /kaniko/executor --dockerfile `pwd`/Dockerfile \
                             --context `pwd` \
                             --destination=rbouikila/myweb:${BUILD_NUMBER}
            '''
          }
        }
      }
    }

    


  }

}
