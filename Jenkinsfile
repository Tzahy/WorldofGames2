pipeline {
agent any
    stages {
        stage('checkout repo from github') {
            steps {
                git 'https://github.com/Tzahy/WorldOfGames2.git'
            }
        }
        stage('build image and run container') {
            steps {
				sh 'docker-compose up -d'
            }
        }
		stage('run test') {
            steps {
				sh 'python tests/e2e.py'
				if (rc != 0) 
				{ 
					sh "echo 'exit code is NOT zero'"
				} 
            }
        }
	}
}


	