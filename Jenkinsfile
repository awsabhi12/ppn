pipeline {
    agent any  
    tools {
        maven 'Maven'  
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: ' https://github.com/awsabhi12/ppn.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package' 
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test' 
            }
        }       
        stage('Run Application') {
            steps {
                 sh 'java -jar target/ppn-1.0-SNAPSHOT.jar'
            }
        }        
    }
    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
