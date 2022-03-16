pipeline {
  agent {
    kubernetes {
      cloud 'Kyma'
      defaultContainer 'jnlp'
    }

  }
  stages {
    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "secret.yml", kubeconfigId: "09a82357-0bf8-47ad-8d8e-b455b30b3ce3")
        }

      }
    }

  }
}