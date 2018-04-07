pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3000:3000' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                //sh 'npm install'
		sh 'uname -a'
		sh 'pwd'
		sh 'touch created_within_docker_agent.txt'
		sh 'ls -al /' 
            }
        }
    }
}

