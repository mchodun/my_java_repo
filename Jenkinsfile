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
				script {
				    currentVersion = sh(script: "cd maciej-module && mvn -q -Dexec.executable=echo -Dexec.args='${project.version}'  --non-recursive exec:exec", returnStdout: true)
				    echo "${currentVersion}"
				}
				echo "building"
			    sh 'cd maciej-module && mvn build-helper:parse-version versions:set -DnewVersion=\\${parsedVersion.majorVersion}.\\${parsedVersion.minorVersion}.\\${parsedVersion.nextIncrementalVersion}'
			    sh 'git commit -m "version updated"'
			    withCredentials([usernamePassword(credentialsId: 'mchodun_github',
                                 usernameVariable: 'username',
                                 passwordVariable: 'password')]){
                    sh "echo ${username}, ${password}"
                }
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
