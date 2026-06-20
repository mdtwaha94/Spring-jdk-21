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
              mvn test
              mvn package
              ls
              '''
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar'
            }
        }
    }
}
