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
        kubeconfig(serverUrl: 'https://api.rdimitrov.promart.shoot.canary.k8s-hana.ondemand.com', caCertificate: 'LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUM5ekNDQWQrZ0F3SUJBZ0lSQUtHdG1lTGR1bFhUeEdyUkRUL3pZcVV3RFFZSktvWklodmNOQVFFTEJRQXcKRlRFVE1CRUdBMVVFQXhNS2EzVmlaWEp1WlhSbGN6QWVGdzB5TVRFeU1ERXhNakV6TVRWYUZ3MHpNVEV5TURFeApNakV6TVRWYU1CVXhFekFSQmdOVkJBTVRDbXQxWW1WeWJtVjBaWE13Z2dFaU1BMEdDU3FHU0liM0RRRUJBUVVBCkE0SUJEd0F3Z2dFS0FvSUJBUURhQVZQZ2pwcjUzcGNnOCs3bmVONmhKQjEwZVJVQmxoMFBCS1lQajVEaExxc2MKV1gzODhjWFhSbExFUkZpWHEvYUJIbGs3czh2NGIrYmxTcndFTHpReE1ZQ2YvSzE3UnpsL1ZwVkNuSHpDYTQ1ZgpmSzREK0xKa3dRaUZHUTdCcElKTmNuOENlUUxvMFozTmhER1RHVlpRVzQ2OVRFNkxtd2xIMjcxanlwNU5YRFNCCm5LUVNFRGdrZDlISXh6TWRZUmdMVDg3TXE3ZmNIRXkvMGlKd1BOOUM5RUZ3eElsdzFiUllTVExuT2pGVnpGWmwKY2FoME5CRHJBcldaMmpEOVkwK3BrcFNsa0dtZHlQNUwyT2I4SUFlMnBxMHU5TFVEMnAxTjdVUUQzaUlMMFlUdwpuTDlJRDlJOHBtTzFuTTQ2ekJTd3FHQzdBK0M2YkNpNEJQMXNpZEFEQWdNQkFBR2pRakJBTUE0R0ExVWREd0VCCi93UUVBd0lCcGpBUEJnTlZIUk1CQWY4RUJUQURBUUgvTUIwR0ExVWREZ1FXQkJUNWxGaUJnOUJGa1NYdnIzd0gKeXNOcTFZY2JaakFOQmdrcWhraUc5dzBCQVFzRkFBT0NBUUVBU1VVMWtPOE9WVHdXaGhuRGdsNVA5Rk45blNvUwpuQ1J2LzNKTzRqSDZuVW03SnRxUVkya3ZXaElJS2FFUUVFcUZweTA0NFRQMC9VSWdsdmErOWFiR1QxVEpiZTdkCmlpV1hjNHhVcmNtV2hxYnZ1eEhrSU1PZWFjVzVOa0FyV1pzK0pacmk0NndJcTJkbWdSZEFJODRwREhrZEJLanEKeFJKeXY4eGJPTVJkZm1PYTZiZVViaVY4Nk1ub3FxRkJFMm10cFIrNmdNeFVWVnc0bU9ZTm5pRzRuRHJOdC8vNAplK3ZvYkRiSDI3eE5sWlN4N2FYdGRHZmgrbVZLU2t4QXNMcGlQZzVyb3htQlQ0QXlFM1FtV1NZMjdPZ2VxSkx5Cjd0Y0k5OWNFWnY5N3o1dkhoQnJVdVZKcUk4TEFvVHgwajEvZGNzOU52OEEvK0xMVlNDUVRsS05MVEE9PQotLS0tLUVORCBDRVJUSUZJQ0FURS0tLS0tCg==', credentialsId: '09a82357-0bf8-47ad-8d8e-b455b30b3ce3')
      }
    }

  }
}