pipeline {
    agent any

    tools {
        maven 'M3'
    }

    stages {
        stage('Long Sleep') {
            steps {
                sh 'sleep 1000'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
