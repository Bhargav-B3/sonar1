pipeline{
    agent any
    environment {
        PATH = "$PATH:/opt/apache-maven-3.9.6/bin"
    }
    stages{
        stage('get code'){
            steps{
                git branch: 'main',
                url:'https://github.com/Bhargav-B3/sonar1'
            }
        }
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
