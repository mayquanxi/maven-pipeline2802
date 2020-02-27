pipeline {
	agent {
		docker {
			image 'maven:3.6.3-jdk-11'
			args '-v /root/.m2:/root/.m2'
			args '-v /root/.m2:/root/.m2'
		}
	}
	stages {
		stage('Building') {
			steps {
				sh 'mvn -B -DskipTests clean package'
			}
		}
	}
}