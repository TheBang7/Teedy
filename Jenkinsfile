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
               sh 'docker build -t teedy2024 .'
            }a
        }
        stage('K8s') {
            steps {
                sh 'kubectl set image deployments/fzb docs=teedy2024'
            }
        }
    }

}
