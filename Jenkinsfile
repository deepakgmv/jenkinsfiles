  
pipeline {
    agent any
    stages {
        stage('one') {
        when{
            environment name: 'ENV', value: 'ICORP'
        }    
            steps {
                echo '$ENV'
            }
        }
	stage('two') {
	when{
            environment name: 'ENV', value: 'ACORP'
        } 
	    steps {
	        echo '$ENV'
            }
	}
	stage('three') {
	when{
            environment name: 'ENV', value: 'PCORP'
        } 
	    steps {
	        echo '$ENV'
	    }
	}
     }
}
