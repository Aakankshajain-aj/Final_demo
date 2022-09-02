pipeline{
   agent any
   environment{
      dockerHome = tool 'My_docker'
	  mavenHome = tool 'My_maven'
	  PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
   }
   stages{
     stage('Checkout'){
	    steps{
		   sh "mvn --version"
		   sh "docker version"
		}
	 }
	 stage('Compile'){
	    steps{
		   sh "mvn clean compile"
		}
	 }
	 stage('Test'){
	     steps{
		    sh "mvn test"
		 }
	 }
	 stage('Package'){
	     steps{
		   sh "mvn package -Dskip Tests"
		 }
	 }
   }
}
