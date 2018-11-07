//import jenkins.model.*
//jenkins = Jenkins.instance

node{
	stage ('SCM Checkout'){
		git 'https://github.com/iDhruven/Patelco'
	}

	stage ('Compile-Package'){
		//Get Maven Home Path
		def mvnHOME = tool name: 'Maven', type: 'maven'
		sh "echo 'Hello'"
		sh "${mvnHOME}/bin/mvn package" 
		sh "echo 'Hello'"
	}
	
	stage('SonarQube analysis') {
    		def mvnHOME = tool name: 'Maven', type: 'maven'
		withSonarQubeEnv('Sonar') {
      		// requires SonarQube Scanner for Maven 3.2+
		sh "${mvnHome}/bin/mvn sonar:sonar" //Publish the SourceCode to SonarQube
      		
   		}
  	}
	
	stage ('Email Notification'){
	}
	
	stage ('Slack Notification'){
	}
	
}
