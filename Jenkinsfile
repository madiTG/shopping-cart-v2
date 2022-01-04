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
						bash './mvn test -D testGroups=unit'
					}
				}
				stage ('Integration Tests') {
					steps {
						bash './mvnw test -D testGroups=integration'
					}
				}
			}
		}
	}	
}
