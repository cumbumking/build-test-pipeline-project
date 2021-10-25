pipeline{
  agent any
  stages{
    stage("checkout"){
      steps{
          checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'prakash', url: 'https://github.com/cumbumking/pipeline-project.git']]])}
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
