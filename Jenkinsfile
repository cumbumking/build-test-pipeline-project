pipeline{
  agent any
  stages{
    stage("checkout"){
      steps{
          checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '76696a43-22cf-4038-8ab9-6bd17c61eb41', url: 'https://github.com/cumbumking/pipe-project.git']]])         }
       }
    stage("bulid"){ 
      steps{
          sh """
            mvn clean
            mvn install
          """
      }
    } 
    stage("test"){ 
      steps{
          sh """
            mvn test
          """
      }
    }
  }
}
