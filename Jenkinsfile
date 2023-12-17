pipeline {
  agent any

  stages {
    stage('message') {
      steps {
        sh 'echo "hello world"'
      }
    }
    
    stage('Checkout Source') {
      steps {
        git 'https://github.com/LeenaRaut13/k8s-files.git'
      }
    }

    stage('Deploying Node App to Kubernetes') {
      steps {
        script {
          sh 'aws eks update-kubeconfig --name sample --region us-east-1'
          sh 'kubectl get ns'
          sh 'kubectl apply -f deployment.yml'
        }
      }
    }
  }
}


