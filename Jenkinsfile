pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-u root -v /root/.m2:/root/.m2'
    }
  }
  stages {
    stage('Build'){
      steps {
        sh 'mvn -e -B -DskipTests clean package'
      }
    }
  }
}
