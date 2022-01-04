pipeline {
	agent any 

	parameters {
		booleanParam(name: "RUN_INTEGRATION_TESTS", defaultValue: true)
	}

	stages {
		stage ('Test') {
			parallel {
				stage ('Unit Test') {
					steps {
						sh './mvn test -D testGroups=unit'
					}
				}
				stage ('Integration Tests') {
					steps {
						sh './mvnw test -D testGroups=integration'
					}
				}
			}
		}
	}	
}
