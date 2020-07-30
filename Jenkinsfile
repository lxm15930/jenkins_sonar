pipeline {
    agent any
	stages {
	   stage('Code Analysis'){
			steps{
				withSonarQubeEnv('sonarqube'){
					bat  'mvn clean sonar:sonar'
					}
				}
　　		}
		stage('Quality Gate'){
			steps{
				script {
					timeout(time:1,unit:'HOURS'){
						sleep(5)
						def qg = waitForQualityGate()
						if (qg.status != 'OK') {
						echo "Status: ${qg.status}"
						error "Pipeline aborted due to quality gate failure: ${qg.status}"
						}
						}
　　				}
				}
			}
		}
}
