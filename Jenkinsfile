pipeline {
    agent any
	stages {
	stage('codeAnalysis'){
	  steps {
	   bat "mvn clean sonar:sonar"
	  }
	}
	}
}