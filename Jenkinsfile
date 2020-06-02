pipeline{
   agent any
   stages{
     stage('checkin from github'){
       steps{
	   git credentialsId: 'Abhinandh-GitHub', url: 'https://github.com/abhinandh/sampleCICD.git'
       }
     }
   }	   
}

