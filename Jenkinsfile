pipeline{
    agent any
    tools {
        maven 'maven'
    }
    stages{
        stage("pull code"){
            steps{
                git 'https://github.com/darshimackey/spring-project.git'
            }
        }
        stage("clean package"){
            steps{
                sh 'mvn clean package'
            }
        }
    }
}