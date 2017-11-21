pipeline  {
  agent {
      label 'slave1'
  }

  stages {
    stage ('Check Maven Installation'){

      steps {
        sh "mvn -v"
      }
    }
    stage  ('Running Unit Tests'){
      steps {
        sh "mvn test"
        }
    }
    stage ('Build Package with Maven'){
      steps {
        sh "mvn package"
      }
      post {
        success {
          archiveArtifacts artifacts: 'target/gs-maven-*.jar', fingerprint: true, onlyIfSuccessful: true
        }
      }
    }

  }
}
