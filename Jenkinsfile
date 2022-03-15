pipeline {
  agent any
  stages {
    stage('GitHub') {
      steps {
        git(url: 'git@github.com:KrisIliev/MongoDB.git', branch: 'main', credentialsId: 'Krisiliev')
      }
    }

    stage('k8 install') {
      steps {
        sh 'curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"'
        sh '''chmod +x kubectl
mkdir -p ~/.local/bin/kubectl
mv ./kubectl ~/.local/bin/kubectl
'''
      }
    }

    stage('K8 Test') {
      steps {
        sh 'kubectl get all'
      }
    }

  }
}