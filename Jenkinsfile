pipeline {
    agent any
    environment {
        MY_ENV_TOKEN = '35d044d2a87a8f9a62b29aff9fc68e261320aa05'
    }
    tools {
        maven 'M2_HOME'
    }
    stages {
        stage('maven clean') {
            steps {
                sh 'mvn clean'
            }
        }
        stage('maven install') {
            steps {
                sh 'mvn install'
            }
        }
        stage('maven compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('maven test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('maven package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('maven sonar') {
            steps {
                sh "mvn sonar:sonar -Dsonar.login=${env.MY_ENV_TOKEN}"
            }
        }
    }
}
