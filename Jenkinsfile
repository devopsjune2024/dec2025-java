pipeline {
    agent any
    // environment {
    //     PATH = "/opt/maven/bin/:$PATH"
    // }
    tools {
        maven 'maven3.9.10'
    }
    stages {
        stage('Manasa_gitcheckout') {
            steps {
                git branch: 'Manasa', url: 'https://github.com/devopsjune2024/dec2025-java.git'
            }
        }
        stage('Manasa_maven-check') {
            steps {
               sh 'mvn --version'
            }
        }   

        stage('Manasa_Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
                sh 'mvn validate'
                sh 'mvn install'
            }
        }         
 
         stage('Manasa_Validation') {
            steps {
                sh 'mvn validate'
            }
        }      
        
    }
}
