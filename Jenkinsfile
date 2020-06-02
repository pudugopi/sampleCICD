pipeline{
   agent any
   stages{
     stage('checkin from github'){
       steps{
	   git credentialsId: 'githublogin', url: 'https://github.com/Yesskarthick/CICD_porcess.git'
       }
     }
     stage('creatin docker image'){
       steps{
	   sh "sudo docker build /var/lib/jenkins/workspace/CICD_process_github/CICD_process/ -t firstapp"
       }
     }
	stage('docker image push'){
		steps{
			withCredentials([string(credentialsId: 'dockerhubcre', variable: 'dockerhub_regis')]) {
            sh "sudo docker login --username karthick24 --password ${dockerhub_regis}"
		}
	    sh "sudo docker push firstapp"
       }
     }   
   }

}

