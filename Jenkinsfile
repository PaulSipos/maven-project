pipeline  {
  agent {
      label 'slave1'
  }

  stages {
    stage ('Check Maven Installation'){

      step {
        sh "mvn -v"
      }
    }
  
  }
}
