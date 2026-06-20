pipeline {
    agent any
    tools {
        maven 'maven'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage ('clone') {
            steps {
                git branch: 'main', url: 'https://github.com/mdtwaha94/Spring-jdk-21.git'
            }
        }
        stage ('build') {
            steps {
              sh '''
              java -version
              javac -version
              mvn -version
              mvn package
              ls
              '''
            }
        }
        stage('Deploy') {
    steps {
        sshagent(credentials: ['ec2-agent-key']) {
            sh '''
                scp target/*.jar user@13.60.31.150:/opt/springboot-app/app.jar
            '''
          }
         }
       }
    }
}
