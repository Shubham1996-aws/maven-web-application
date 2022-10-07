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
	

}
}
