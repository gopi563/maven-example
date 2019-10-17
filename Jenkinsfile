pipeline {
    agent any 
    stages {
        stage('Code Checkout') { 
            steps {
                git credentialsId: 'github', url: 'git@github.com:gopi563/maven-example.git'
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
        stage('Package') { 
            steps {
              withMaven(jdk: 'jdk1.8', maven: 'maven3.6.1') {
               sh 'mvn package'
             }  
            }
        }
        stage('Docker Image') { 
            steps {
             sh 'echo docker image is build'   
            }
        }
        stage('Deploy to Dev') { 
            steps {
             sh 'echo Deploy to Dev'   
            }
        }
        stage('Deploy to prod') { 
            steps {
              sh 'echo Deploy to Prod'  
            }
        }
    }
