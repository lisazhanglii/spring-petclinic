pipeline {
    agent any
    stages {
            stage('Checkout Source') {
                steps {
                    script {
                        git branch: 'main',
                            url: 'https://github.com/lisazhanglii/spring-petclinic.git'
                    }
                }
            }
            stage('Build petclinic.jar') {
                    steps {
                        // Build the .jar file using Maven
                        sh './mvnw package -DskipTests'
                    }
                
                }
                
        //     stage('SonarQube Analysis') { 
        //     steps {
        //         script {
        //             withSonarQubeEnv('devopsenv') {
        //                 sh "${tool('sonar-scanner')}/bin/sonar-scanner -Dsonar.projectKey='devops' -Dsonar.projectName='devops'"
        //             }
        //         }
        //     }
        // }
        }
            post {
                    success {
                        echo 'Build and analysis successful.'
                    }
                    failure {
                        echo 'Build or analysis failed.'
                    }
                }
    }
