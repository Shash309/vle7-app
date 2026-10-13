pipeline {
  agent any
  stages {
    stage('Build')  { steps { sh 'docker build -t myapp:latest .' } }
    stage('Load')   { steps { sh 'minikube image load myapp:latest' } }
    stage('Deploy') { steps { sh 'kubectl apply -f deployment.yaml && kubectl rollout restart deploy/myapp' } }
  }
}
