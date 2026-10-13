pipeline {
  agent any
  stages {
    stage('Build')  { steps { sh 'docker build -t myapp:latest .' } }
    stage('Load')   { steps { sh 'docker save myapp:latest | docker exec -i minikube ctr -n k8s.io images import -' } }
    stage('Deploy') { steps { sh 'kubectl apply -f deployment.yaml && kubectl rollout restart deploy/myapp' } }
  }
}
