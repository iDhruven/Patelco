import jenkins.model.*
jenkins = Jenkins.instance

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
		def mvnHOME = tool name: 'Maven', type: 'maven'
      		// requires SonarQube Scanner for Maven 3.2+
		sh "${mvnHome}/bin/mvn sonar:sonar"
      		
   		}
  	}
	
	stage ('Email Notification'){
	}
	
	stage ('Slack Notification'){
	}
	
}
