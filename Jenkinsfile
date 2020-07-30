pipeline {
    agent any
	stages {
	stage('code Analysis'){
	  steps {
	   withSonarQubeEnv('sonarqube'){
	   bat """
	     mvn clean verify sonar:sonar \
		 -Dsonar.login=11f571e00b72b08900b3fc1f8d41f8a3af2caaf8
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