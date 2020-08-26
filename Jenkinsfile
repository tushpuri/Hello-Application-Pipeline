pipeline {  
	agent any
	
	stages {
		stage('Build Application') {
	        	steps {
	                	bat 'mvn clean install'
			}
		}
	        stage('Test') {
	               steps {
	                  	echo 'Test Appplication...' 
        		  	bat 'mvn clean test'      
        		}   
		}
               stage('Deploy CloudHub') {
		       steps {
			       echo 'Deploying only because of code commit...'
			       bat 'mvn package deploy -DmuleDeploy -Danypoint.environment=Sandbox -Danypoint.username=tusharpuri002 -Danypoint.password=TushP0101 -Danypoint.workers=1 -Danypoint.workersType=MICRO -Danypoint.applicationName=Hello-Application-2 -Danypoint.muleVersion=4.3.0 -DobjectStoreV2=true'
		       }    
	       }  
	}
}
