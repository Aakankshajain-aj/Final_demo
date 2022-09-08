//def docker_url = "https://hub.docker.com/repository/docker/aakankshasamota/finaldemo/general"
pipeline{	
   agent any
    stages{
     stage('Build') {
             steps {
                // Get some code from a GitHub repository
                git 'https://github.com/Aakankshajain-aj/Final_demo.git'
 	    }		    
       }
     stage('Checkout'){
	    steps{
		   //bat "mvn --version"
		    bat "docker version"
		 }
	 }
	 stage('Compile'){
	    steps{
		   bat "mvn clean"
		}
	 }
// 	 stage('Test'){
// 	     steps{
// 		    bat "mvn test"
// 		 }
// 	 }
	 stage('Package'){
	     steps{
		   bat "mvn package"
		 }
	 }
	 stage('Docker Image'){
		  steps{
			  script{
				  dockerImage = docker.build("aakankshasamota/currency-exchange:${env.BUILD_TAG}")
			    }
		    }
	    }
	    stage('Docker Push Image'){
		    steps{
			    script{
 				    //docker scan --accept-license --version
				   // docker scan currency-exchange"{$env.BUILD_TAG}"
				   // docker.withRegistry(' ','dockerhub'){
				    //dockerImage.push();
				    //dockerImage.push('latest');
				    docker.withRegistry('https://hub.docker.com/repository/docker/aakankshasamota/finaldemo', 'dockerhub') {            
                                    dockerImage.push("${env.BUILD_NUMBER}");
			            dockerImage.push('latest');
					    
				    }
			    }
		    }
	    }    
  }
}
