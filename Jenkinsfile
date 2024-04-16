pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven 'maven-3.9.6'
    }

    stages {
        stage('Git Clone') {
            steps {
               git credentialsId: 'git1', url: 'https://github.com/springbreeze8518/ksrepo9.git' 
            }
			}
		stage('Maven Version') {
            steps {
               sh 'mvn --version' 
            }
			}
		stage('Maven Clean') {
            steps {
               sh 'mvn clean' 
            }
			}
		stage('Maven Validate') {
            steps {
               sh 'mvn validate' 
            }
			}
		stage('Maven Compile') {
            steps {
               sh 'mvn compile' 
            }
			}
        stage('Maven Test') {
            steps {
               sh 'mvn test' 
            }
			}
		stage('SonarScan') {
            steps {
               sh 'mvn sonar:sonar -Dsonar.host.url=http://54.83.164.94:9000 -Dsonar.login=9e7d6ee238ffa3aaed89d10959ef1fb167f981ef' 
            }
			}
		stage('Maven package') {
            steps {
               sh 'mvn package' 
            }
			}
		stage('Maven Deploy') {
            steps {
               sh 'mvn deploy' 
            }
        }
		
    }
}
   

