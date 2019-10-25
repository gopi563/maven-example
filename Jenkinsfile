pipeline {
    agent any 
    stages {
        stage('Code Checkout') { 
            steps {
                git credentialsId: 'github', url: 'https://github.com/gopi563/maven-example.git'
            }
        }
        stage('Build') { 
            steps {
              withMaven(jdk: 'jdk1.8', maven: 'maven3.6.1') {
               sh 'mvn clean compile'
             }
            }
        }
        stage('Test') { 
            steps {
               withMaven(jdk: 'jdk1.8', maven: 'maven3.6.1') {
               sh 'mvn test'
             }  
            }
        }
            stage('CODE ANALYSIS') { 
            steps {
            withMaven(jdk: 'jdk1.8', maven: 'maven3.6.1') {
            sh 'mvn sonar:sonar \
                    -Dsonar.projectKey=388cc22c82db244a2bf4d4303cc769b2592794d0 \
                    -Dsonar.organization=sonarorg12 \
                    -Dsonar.host.url=https://sonarcloud.io \
                    -Dsonar.login=3c93b37ca7369b45db1b038d832ce3bebe2cd201'
        }
            }
            }
   stage('Archive to Jfrog') {
   } 
   stage('Docker Image') {
   } 
   stage('Deploy to Prods') {
   } 
}
 

