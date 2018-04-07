pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3000:3000 -e npm_config_cache=/var/lib/jenkins/workspace/simple-node-js-react-npm-app/.npm' 
            //NOTE: the location of the npm cache needs to be changed because otherwise it tries to put it into the root dir	    
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

