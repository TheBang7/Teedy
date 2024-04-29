pipeline{
  agent any
  stages('Build'){
    steps{
      sh 'mvn -B -DskipTests clean package'
    }
  }
}