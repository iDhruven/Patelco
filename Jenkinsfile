node{
	stage ('SCM Checkout'){
		git 'https://github.com/iDhruven/Patelco'
	}

	stage ('Compile-Package'){
		//Get Maven Home Path
		def mvnHOME = tool name: 'Maven', type: 'maven'
		sh "${mvnHOME}/bin/mvn package" 
	}
	
	stage ('Email Notification'){
	}
	
	stage ('Slack Notification'){
	}
}
