  
pipeline {
    agent any
    stages {
        stage('one') {
        when{
            environment 'Icorp'
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
