pipeline {
    agent any
    stages {
        stage("get code"){
            steps{
               git 'https://github.com/ramk95/hello-world.git'
            }
        }
        stage("build code"){
            steps{
              sh "mvn clean install"
            }
        }
        stage("deploy"){
            steps{
              sshagent(['tomcat-user']) {
                 sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war tomcat@3.96.211.107:/usr/local/apache-tomcat-9.0.46/webapps"
                 
                }
            }
        }
    }
}
