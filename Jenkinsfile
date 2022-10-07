pipeline{

agent any

tools{
maven 'maven3.8.2'

}



stages{

  stage('CheckOutCode'){
    steps{
    git 'https://github.com/Shubham1996-aws/maven-web-application.git'
	
	}
  }
  
  stage('Build'){
  steps{
  sh  "mvn clean package"
  }
  }

  
  
  stage('DeployAppIntoTomcat'){
  steps{
  sshagent(['795e3c67-7d79-47c5-b703-337e413411d2']) {
   sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war   ubuntu@172.31.15.89:/opt/apache-tomcat-8.5.82/webapps/"    
  }
  }
  }
}
  
