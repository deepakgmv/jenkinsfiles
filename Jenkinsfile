  
pipeline {
    agent any
    stages {
        stage('one') {
        when{
            $ENV 'Icorp'
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
