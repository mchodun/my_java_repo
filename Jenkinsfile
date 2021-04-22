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
			    sh '''#!/bin/bash
                                 ls
                         '''
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
