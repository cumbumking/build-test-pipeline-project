pipeline{
  agent any
  stages{
    stage("checkout"){
      steps{
          checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'cumbumking', url: 'https://github.com/cumbumking/maven-proj.git']]])
         }
       }
    stage("bulid"){ 
      steps{
          sh """
            mvn clean
            mvn install
          """
      }
    }
  }
}
