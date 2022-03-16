pipeline {
  agent {
    kubernetes {
      	cloud 'kubernetes'
      	defaultContainer 'jnlp'
      }
    }
  stages {
    stage('GitHub') {
      steps {
        git(url: 'git@github.com:KrisIliev/MongoDB.git', branch: 'main', credentialsId: 'Krisiliev')
      
    }
  stages {
    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "hellodocker.yml", kubeconfigId: "MINIKUBECONFIG")
        }
      }
    }
  
}