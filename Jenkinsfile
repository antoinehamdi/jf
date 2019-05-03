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
				configFileProvider(
    				[configFile(fileId: '9253f13d-e2f6-4041-b855-9bc2ee3f0b2b', variable: 'MAVEN_SETTINGS')]) {
    				sh 'mvn -s $MAVEN_SETTINGS deploy'
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