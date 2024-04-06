pipeline{
    agent any
    environment {
        PATH = "$PATH:/opt/apache-maven-3.9.6/bin"
    }
    stages{
        stage('build'){
            steps{
                sh'mvn clean package'
            }
        }
        stage('Sonarqube Analaysis'){
            steps{
                withSonarQubeEn('My SonarQube Server'){
                    sh'mvn sonar:sonar'
                }
            }
        }
    }
}
