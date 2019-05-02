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
				sh "echo 1"
			}
		}
		stage('2') {
			steps {
				sh "echo 2"
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