pipeline {
    agent any
	stages {
	stage('code Analysis'){
	  steps {
	   withSonarQubeEnv('sonarqube'){
	   bat """
	     mvn clean verify sonar:sonar \
		 -Dsonar.login=admin \
		 -Dsonar.password=admin
		"""
		}
	  }
	}
	
	stage('Quality Gate'){
			steps{
				script {
					timeout(time:1,unit:'HOURS'){
						waitForQualityGate abortPipeline: true						
						}
					}
				}
			}
		}
}