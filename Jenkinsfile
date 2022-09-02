pipeline{
   agent any
 //  environment{
   //   dockerHome = tool 'My_docker'
	//  mavenHome = tool 'My_maven'
	//  PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
  // }
//    stages{
//       stage('Build') {
//             steps {
//                 // Get some code from a GitHub repository
//                 git 'https://github.com/Aakankshajain-aj/Final_demo.git'
// 	    }		    
//       }
     stage('Checkout'){
	    steps{
		   //bat "mvn --version"
		    bat "docker version"
		}
	 }
// 	 stage('Compile'){
// 	    steps{
// 		   bat "mvn clean"
// 		}
// 	 }
// 	 stage('Test'){
// 	     steps{
// 		    bat "mvn test"
// 		 }
// 	 }
// 	 stage('Package'){
// 	     steps{
// 		   bat "mvn package"
// 		 }
// 	 }
	
   }
}
