pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-u root'
    }
  }
  stages {
    stage('Build'){
      steps {
        sh 'mvn -e -B -DskipTests clean package'
      }
    }
    stage('Test'){
      steps {
        sh 'mvn test'
      }
      post {
        always {
          junit 'target/surefire-reports/*.xml'
        }
      }
    }
  }
}


