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
                 sh "scp -i /var/lib/jenkins/tt.key webapp/target/webapp.war ec2-user@3.96.211.107:/usr/local/apache-tomcat-9.0.46/webapps/app.war"
            }
        }
    }
}
