pipeline {
    agent any
    stages {
        stage('Code Analysis'){
　　		steps{
				withSonarQubeEnv('sonarqube'){
					bat  '''
					 mvn clean verify sonar:sonar \
					 -Dsonar.login=0d01ad741b3f156f7e9ff62257863ed85c6c5d2c \
　　				 -Dsonar.host.url=http://127.0.0.1:9000
　　					'''
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
