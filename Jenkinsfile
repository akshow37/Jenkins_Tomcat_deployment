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
                
               deploy adapters: [tomcat9(credentialsId: 'Tom_Pass', path: '', url: 'http://18.219.135.14:8080/')], contextPath: 'myapp', war: '"**/*.war'
            }
        }
    }
}
