pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Building image') {
            steps{
               sh 'docker build -t teedy2024_manual .'
            }
        }
        stage('K8s') {
            steps {
                sh 'kubectl expose deployment hello-node --type=LoadBalancer --port=8085'
                sh 'minikube service hello-node'
                sh 'kubectl set image deployments/hello-node docs=sismics/docs:latest'
            }
        }
    }
}
