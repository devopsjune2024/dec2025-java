pipeline {
    agent any
    // environment {
    //     PATH = "/opt/maven/bin/:$PATH"
    // }
    tools {
        maven 'maven3.9.10'
    }
    stages {
        stage('gitcheckout') {
            steps {
                git branch: 'main', url: 'https://github.com/devopsjune2024/dec2025-java.git'
            }
        }
        stage('maven-check') {
            steps {
               sh 'mvn --version'
            }
        }   

        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
                sh 'mvn validate'
                sh 'mvn install'
            }
        }         
 
         stage('Validation') {
            steps {
                sh 'mvn validate'
            }
        }      
        
    }
}
