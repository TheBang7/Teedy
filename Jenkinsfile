pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('K8s') {
            steps {
                sh 'kubectl set image deployments/fzb fzb-65488fc86d-7nmwv=teedy_local:v1.0'
            }
        }
    }

}
