pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                println "Build WORKSPACE ${WORKSPACE}"
                sh '''
                ls -al && pwd
                ./mvnw clean install -DskipTests=true
                docker build -t "spring-boot-websocket:chat-demo" .
                docker images
                '''
            }
        }
    }
}
