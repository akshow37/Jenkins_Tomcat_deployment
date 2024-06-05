pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp && mvn test'
            }
        }
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'Tom_Pass', path: '', url: 'http://3.145.172.149:8080/')], contextPath: 'Ak_app', war: '**/*.war'
            }
        }
    }
}
