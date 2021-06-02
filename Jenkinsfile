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
              sshagent(['test-key']) {
                 sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war tomcat@3.96.211.107:/tmp/webapps/"
                 
                }
            }
        }
    }
}
