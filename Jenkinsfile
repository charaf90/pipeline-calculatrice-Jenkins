pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
		environment {
   		 PATH = "/usr/local/bin:$PATH"
                	docker {
                    	image 'python:3.8-alpine3.16'
                	}
		}
            }
            steps {
		sh 'echo $PATH'
                sh 'python3.8 -m py_compile sources/prog.py sources/calc.py'
                stash(name: 'compiled-results', includes: 'sources/*.py*')
            }
        }
    }
}
