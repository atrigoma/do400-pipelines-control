pipeline {
    agent {
        node {
            label 'nodejs'
        }
    }
    parameters {
       booleanParam(name: "RUN_FRONTENDS_TEST", defaultValue: true)
    }
    stages {
        stage('Run Tests') {
            parallel {
                stage('Backend Tests') {

                    steps {
		        echo 'running backend test...'
                        sh 'node ./backend/test.js'
                    }
                }
                stage('Frontend Tests') {
		    when { expression { params.RUN_FRONTENDS_TEST } }
                    steps {
		        echo 'running frontend test...'
                        sh 'node ./frontend/test.js'
                    }
                }
            }
        }
	stage('Deploy') {
	    when {
                expression { env.GIT_BRANCH == 'origin/main' }
            }
            steps {
                echo 'Deploying...'
            }
	}
    }
}
