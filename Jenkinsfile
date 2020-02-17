  
pipeline {
    agent any
    stages {
        stage('Preparation') {
        when{
            environment name: 'ENV', value: 'ICORP'
        }    
            steps {
                SONAR_HOST_URL="https://sonarqube-be.balgroupit.com"
SOURCES="src"
BINARIES="target/classes" 
        
                deleteDir()
                git branch: 'master', credentialsId: 'TFS', url:'http://svw-me-source01:9091/tfs/DefaultCollection/Baloise/_git/MDM'
            }
        }
	stage('Build') {
	when{
            environment name: 'ENV', value: 'ICORP'
        } 
	    steps {
	        withMaven(jdk: 'jdk8', maven: 'maven_3_2_5_pipeline', mavenOpts: '-Xmx2048m -XX:MaxPermSize=512m') {
                    sh 'mvn clean install'
            }
	}
	stage('Package') {
	when{
            environment name: 'ENV', value: 'ICORP'
        } 
	    steps {
	        build 'MDM_Package'
	    }
	}
	stage('Sonar Analysis') {
	when{
            environment name: 'ENV', value: 'ICORP'
        } 
	    steps {
	        withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'SonarAdmin',usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]) {
                withMaven(jdk: 'jdk8', maven: 'maven_3_2_5_pipeline', mavenOpts: '-Xmx2048m -XX:MaxPermSize=512m') {
                    //sh "mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.1.1:sonar -f atlas-cleva/pom.xml -Dsonar.exclusions=${SONAR_EXCLUSIONS} -Dsonar.host.url=${SONAR_HOST_URL} -Dsonar.login=$USERNAME -Dsonar.password=$PASSWORD"
                }
        }     
	    }
	}
	stage('ICORP_Deployment') {
	when{
            environment name: 'ENV', value: 'ICORP'
        } 
	    steps {
	        build job: 'MDM_Deployer', parameters: [string(name: 'Env', value: 'icorp')]
	    }
	}
	stage('ACORP_Deployment') {
	when{
            environment name: 'ENV', value: 'ACORP'
        } 
	    steps {
	        build job: 'MDM_Deployer', parameters: [string(name: 'Env', value: 'acorp')]
	    }
	}
	stage('PCORP_Deployment') {
	when{
            environment name: 'ENV', value: 'PCORP'
        } 
	    steps {
	        build job: 'MDM_Deployer', parameters: [string(name: 'Env', value: 'pcorp')]
	    }
	}
     }
}
