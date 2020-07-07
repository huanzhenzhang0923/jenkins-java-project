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
                deploy adapters: [tomcat7(path: '', url: 'http://ec2-18-216-240-0.us-east-2.compute.amazonaws.com:8080/')],
                contextPath: 'javawebapp',
                war: '**/java-web-project.war'
            }
        }
    }
}
