pipeline {
	agent {
		docker {
			image 'maven:3.6.3-jdk-11'
		}
	}
	stages {
		stage('Building') {
			steps {
				sh 'mvn -B -DskipTests clean package'
			}
		}
	    stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/maven-archiver/pom.properties'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}