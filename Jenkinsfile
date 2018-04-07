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
                //NOTE: this runs as expected in the new node:6-alpine container
		//      but the jenkins maps the home folder to the pipeline's home
                //      In this case the pipleine is hosted locally, not in a docker, 
                //      hance it requires permissions to run the npm. added jenkins user the correct group to solve this issue.
                sh 'npm install'
		//sh 'uname -a'
		//sh 'pwd'
		//sh 'touch created_within_docker_agent.txt'
		//sh 'ls -al /' 
            }
        }
    }
}

