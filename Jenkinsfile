pipeline{
   agent any
   stages{
     stage('checkin from github'){
       steps{
	   git credentialsId: 'Abhinandh-GitHub', url: 'https://github.com/abhinandh/sampleCICD.git'
       }
     }
	 stage('creatin docker image'){
      steps{
	  sh "sudo docker build /var/lib/jenkins/workspace/SamplePythonProject -t firstapp"
      }
     }
	 stage('docker image push'){
	steps{
	  withCredentials([string(credentialsId: 'abhinandh1991', variable: 'DockerHub-Password')]) {
          sh "sudo docker login -u abhinandh1991 -p ${DockerHub-Password}"
	  sh "sudo docker push firstapp"
		}
	  }
     }  
   }	   
}
