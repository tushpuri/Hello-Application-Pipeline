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
        					  	bat 'mvn test'      
        					}   
        			  }
               stage('Deploy CloudHub') {
                         
                              steps {
                                      echo 'Deploying only because of code commit...'      
                                      bat 'mvn package deploy -DmuleDeploy -Dusername=tusharpuri002 -Dpassword=TushP0101 -Denvironment=Sandbox -DworkerType=Micro -Dworkers=1 -DobjectStoreV2=true'      
                                   	}    
                              }  
                      }
            }
