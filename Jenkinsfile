  
pipeline {
    agent any
    stages {
        stage('one') {
        when{
            environment name: 'ENV', value: '$ENV'
        }    
            steps {
                echo '$ENV'
            }
        }
	stage('two') {
	    steps {
	        echo '$ENV'
            }
	}
	stage('three') {
	    steps {
	        echo '$ENV'
	    }
	}
     }
}
