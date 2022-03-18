pipeline {
  agent { 
    kubernetes {
      label 'Kyma-Test-Pipeline_9-sq3l6'
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
