pipeline {
	agent any
	stages {
	    stage ('maven version') {
	        steps {
                sh 'mvn -v'
	        }
	    }
		stage ('build') {
			steps {
				echo "building"
				echo "building 2"
			}
		}
		stage ('test') {
			steps {
				echo "testing"
			}
		}
		stage ('deploy') {
			steps {
				echo "deloying"
			}
		}
	}
}
