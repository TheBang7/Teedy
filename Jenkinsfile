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
                sh 'kubectl set image deployments/hello-node container-name=teedy_manual04'
            }
        }
    }
}
