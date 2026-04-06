pipeline {
    agent any   // run on any available machine (your EC2)

    stages {

        stage('Checkout') {
            steps {
                echo 'Pulling code from GitHub...'
                git branch: 'main', url: 'https://github.com/Giteshag27/jenkins-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Compiling Java code...'
                sh 'javac Hello.java'
            }
        }

        stage('Test') {
            steps {
                echo 'Running program...'
                sh 'java Hello'
            }
        }

        stage('Package') {
            steps {
                echo 'Creating jar file...'
                sh 'jar cf app.jar Hello.class'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}