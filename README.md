pipeline {
    agent any
   
    tools {
        maven 'Maven'
        jdk 'JDK'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/vinay-s-14/exp6.git'

            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
    }
   
}
