node{
	stage ('SCM Checkout'){
		git 'https://github.com/iDhruven/Patelco'
	}

	stage ('Compile-Package'){
		//Get Maven Home Path
		def mvnHOME = tool name: 'Maven', type: 'maven'
		sh "${mvnHOME}/bin/mvn package" 
	}
	
	stage('SonarQube analysis') {
    		withSonarQubeEnv('Sonar') {
      		// requires SonarQube Scanner for Maven 3.2+
		sh "${mvnHome}/bin/mvn sonar:sonar"
      		
   		}
  	}
	
	stage ('Email Notification'){
	}
	
	stage ('Slack Notification'){
	}
	
  	stage('SCM') {
    	git 'https://github.com/foo/bar.git'
  	}
  	

	
}
