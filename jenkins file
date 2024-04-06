pipeline {
        agent none
        stages {
          stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('sonarqube-9.9.4.87374') {
                sh 'mvn clean package sonar:sonar'
              }
            }
          }
