pipeline{
  agent any
  stages{
    stage("checkout"){
      steps{
          checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '513f1136-7d2f-49ed-a101-e1c02df43536', url: 'https://github.com/cumbumking/pipeline-project.git']]])
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
    stage("test"){ 
      steps{
          sh """
            mvn test
          """
      }
    }
    stage("package"){ 
      steps{
          sh """
            mvn package
          """
      }
    }
     stage("deploy"){ 
      steps{
          sh """
            mvn deploy
          """
      }
    }
  }
}   
