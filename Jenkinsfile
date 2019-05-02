pipeline {
	agent {
		label "master"
	}

	tools {
		maven "maven3"
	}
	options {
		timestamps()
	}
	stages {
		stage('checkout') {
			steps {
				git branch: 'master',
    			    credentialsId: 'ed8c2959-59cf-42c3-ac22-1b25026d26f0',
                    url: 'https://github.com/antoinehamdi/hits.git'
			}
		}
		stage('test') {
			steps {
				sh "mvn clean test"
			}
		}
		stage('build') {
			steps {
				sh "mvn clean install"
			}
		}
		stage('deploy') {
			steps {
				
    				sh 'mvn -s settings.xml deploy'
				}
			}
		}
	}
    post { 
        always { 
            echo 'THE END'
        }
        unsuccessful {
        	echo 'RATE'
        }

    }
}