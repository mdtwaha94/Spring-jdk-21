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
              mkdir -p /opt/springboot-app
              cp target/demo-0.0.1-SNAPSHOT.jar /opt/springboot-app/app.jar
              ls -l /opt/springboot-app
              '''
            }
        }
    }
}
