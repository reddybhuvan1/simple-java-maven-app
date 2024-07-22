pipeline {
    agent any

    stages {
        stage('SCM') {
            steps {
                echo 'fetching the code'
			    git changelog: false, poll: false, url: 'https://github.com/TechWithKhanam/simple-java-maven-app.git'
            }
        }
		stage('BUILD') {
            steps {
                echo 'building the project'
				bat 'mvn clean install'
            }
        }
		stage('TEST') {
            steps {
                echo 'testing the project'
				 bat 'mvn test'
            }
        }
		stage('DEPLOY') {
            steps {
                echo 'deploying the project'
				 bat 'mvn deploy'
            }
        }
    }
}
