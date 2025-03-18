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
        stage("stop existing application"){
            steps{
                sh "pkill -f 'spring_app_sak-0.0.1-SNAPSHOT.jar' || true"
            }
        }
        stage("deploy the application"){
            steps{
                sh "java -jar target/spring_app_sak-0.0.1-SNAPSHOT.jar"
            }
        }
        stage("deploy") {
            steps {
                sh "java -jar target/spring_app_sak-0.0.1-SNAPSHOT.jar > app_output.log 2>&1 &"
                sh "tail -f app_output.log"
                    }
            }      
    }
}
