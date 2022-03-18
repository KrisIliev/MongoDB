pipeline {
  agent any { 
    kubernetes {
      cloud 'Kyma'
      defaultContainer 'jnlp'
    }

  }
  stages {
    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "mongodb-secret.yaml", kubeconfigId: "KumaKubeconfig")
        }

      }
    }

  }
}
