pipeline{

agent any

tools{
maven 'maven_3.8.6'

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
  sshagent(['cd6178fb-4d7c-4860-8039-8bedb78c427b']) {
   sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war   ubuntu@172.31.15.89:/opt/apache-tomcat-8.5.82/webapps/"    
  }
  }
  }
}
}
