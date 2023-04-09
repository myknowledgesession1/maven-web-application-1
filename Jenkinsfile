pipeline {
    agent any

       tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven"
       }
    stages {
        stage('git') {
            steps {
                git branch: 'development', url: 'https://github.com/myknowledgesession1/maven-web-application-1.git'
            }
        }
         stage('build') {
            steps {
                sh "mvn clean package"
            }
        }
         stage('sonar report') {
            steps {
                sh  "mvn clean sonar:sonar"
            }
        }
        stage('nexus upload') {
            steps {
                sh  "mvn deploy"
            }
        }
        stage('tomcat deploy') {
            steps {
                sshagent(['f594a1eb-c3dc-4c62-a059-67c92769435d']) {
                 sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.129.58.84:/opt/apache-tomcat-9.0.73/webapps"
                }
            }
        }
    }
}
