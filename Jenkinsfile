pipeline {
	agent any
	tools {
            maven 'mvn 3.6.3'
            jdk 'jdk8'
        }
	stages {
	    stage ('maven version') {
	        steps {
                sh 'mvn -v'
	        }
	    }
		stage ('build') {
			steps {
				echo "building"
			    sh 'cd maciej-module'
			    sh 'mvn versions:set -DnewVersion=1.0.3-eluwina'
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
