  
pipeline {
    agent any
    stages {
	when{
            $ENV = 'Icorp'
        }    
        stage('one') {
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
