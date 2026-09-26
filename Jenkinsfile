pipeline {
    agent any

    stages{
        stage('Clone-Repo'){
            steps{
                checkout scm
            }
        }

        stage('build'){
            steps{
                sh 'mvn install'
            }
        }

        stage('Compile'){
            steps{
                sh 'mvn clean compile'
            }
        }

        stage('Package as WAR'){
            steps{
                sh 'mvn package'
            }
        }

        stage('Deployment'){
            steps{
                sh 'scp target/hello-maven.war root@32.192.179.211:/home/ubuntu/tomcat/apache-tomcat-11.0.25/webapps'
            }
        }
    }
}
