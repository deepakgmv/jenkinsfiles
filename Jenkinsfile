  
pipeline {
    agent any
    stages {
        stage('Preparation') {
        when{
            environment name: 'ENV', value: 'ICORP'
        }    
            steps {
                echo '$ENV'
            }
        }
	stage('Build') {
	when{
            environment name: 'ENV', value: 'ICORP'
        } 
	    steps {
	        echo '$ENV'
            }
	}
	stage('Package') {
	when{
            environment name: 'ENV', value: 'ICORP'
        } 
	    steps {
	        echo '$ENV'
	    }
	}
	stage('Sonar Analysis') {
	when{
            environment name: 'ENV', value: 'ICORP'
        } 
	    steps {
	        echo '$ENV'
	    }
	}
	stage('Sonar Analysis') {
	when{
            environment name: 'ENV', value: 'ICORP'
        } 
	    steps {
	        echo '$ENV'
	    }
	}
	stage('ICORP_Deployment') {
	when{
            environment name: 'ENV', value: 'ICORP'
        } 
	    steps {
	        echo '$ENV'
	    }
	}
	stage('ACORP_Deployment') {
	when{
            environment name: 'ENV', value: 'ACORP'
        } 
	    steps {
	        echo '$ENV'
	    }
	}
	stage('PCORP_Deployment') {
	when{
            environment name: 'ENV', value: 'PCORP'
        } 
	    steps {
	        echo '$ENV'
	    }
	}
     }
}
