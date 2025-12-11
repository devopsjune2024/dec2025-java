pipeline {
    agent any
    // environment {
    //     PATH = "/opt/maven/bin/:$PATH"
    // }
    tools {
        maven 'maven3.9.10'
    }
    stages {
        stage('Shiva-GIT') {
            steps {
                git branch: 'main', url: 'https://github.com/devopsjune2024/dec2025-java.git'
            }
        }
        stage('Shiva-maven-check') {
            steps {
               sh 'mvn --version'
            }
        }   

        stage('Shiva-BUILD') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }         
 
         stage('Validation') {
            steps {
                sh 'mvn validate'
            }
        }      
        
    }
}
