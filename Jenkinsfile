pipeline{

agent any

tools{
git 'Default'
maven 'maven'

}

stages{

  stage('CheckOutCode'){
    steps{
    git branch: 'deployment', credentialsId: 'a1d3d239-86fe-4efe-aac4-d118ae4f82b4', url: 'https://github.com/myknowledgesession1/maven-web-application-1.git'
	
	}
  }
/*
  stage('Build'){
  steps{
  sh  "mvn clean package"
  }
  }

 stage('ExecuteSonarQubeReport'){
  steps{
  sh  "mvn clean sonar:sonar"
  }
  }
  
  stage('UploadArtifactsIntoNexus'){
  steps{
  sh  "mvn clean deploy"
  }
  }
  
  stage('DeployAppIntoTomcat'){
  steps{
  sshagent(['9ecd6077-da0e-42b0-b3ef-fcbed6a76cef']){
   sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@18.191.251.203:/opt/apache-tomcat-9.0.73/webapps"   
  }
  }
  }*/
}//Stages Closing
}//Pipeline closing
