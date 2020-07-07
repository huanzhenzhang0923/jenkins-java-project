pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh "/opt/maven/bin/mvn clean package"
            }
        }
        stage('Deploy') {
            steps {
                deploy adapters: [tomcat7(credentialsId: '355c9ad2-91c5-46d1-bd86-5ea915b18f21', path: '', url: 'http://ec2-18-223-238-208.us-east-2.compute.amazonaws.com:8080/')], 
                       contextPath: 'javawebapp', 
                       war: '**/java-web-project.war'
            }
        }
    }
}
