pipeline {
	agent {
		label "master"
	}
	tools {
		maven "maven3"
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
				mvn test
			}
		}
		stage('3') {
			steps {
				sh "echo 3"
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