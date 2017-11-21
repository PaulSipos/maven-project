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
    stage ('Build Package with Maven'){
      steps {
        sh "mvn package"
      }
    }

    stage ('Archive the package'){
      steps {
        archiveArtifacts artifacts: 'target/gs-maven-*.jar', fingerprint: true, onlyIfSuccessful: true
      }
    }

  }
}
