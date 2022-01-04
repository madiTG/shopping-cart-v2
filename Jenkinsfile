pipeline {
	agent { 
		any 
	}
	
	parameters {
		booleanParam(name: "RUN_INTEGRATION_TESTS", defatultValue: true)
	}

	stages {
		stage ('Test') {
			parallel {
				stage ('Unit Test') {
					steps {
						./mvn test -D testGroups=unit
					}
				}
				stage ('Integration Tests') {
					steps {
						./mvnw test -D testGroups=integration
					}
				}
			}
		}
	}	
}
