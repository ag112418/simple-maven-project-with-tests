pipeline {
    agent any
    tools {
        maven "M3"
    }

    stages {
        stage('Long Running Work') {
            steps {
                echo 'Starting long-running task: sleeping for 1000 seconds...'
                sleep 1000
            }
        }

        stage('Build') {
            steps {
                sh "mvn -Dmaven.test.failure.ignore=true clean package"
            }
            post {
                success {
                    junit '*/target/surefire-reports/TEST-.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}
