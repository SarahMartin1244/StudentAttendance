pipeline {
    agent any

    tools {
            // Maven installation name in Jenkins
            maven 'Maven_setup'
        }

    stages {
        stage('Build') {
            steps {
                script {
                    // Clean workspace before fetching
                    deleteDir()

                    //  fetch and checkout the code
                     // git 'https://github.com/SarahMartin1244/StudentAttendance.git'
                   checkout scm

                    // Full path to Maven executable
                     sh '/usr/local/bin/mvn clean install'
                }
            }
        }

        stage('Tests') {
            steps {
                script {
                    // Run JUnit tests using Maven
                    sh 'mvn test'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }

    post {
        always {
            // Clean up workspace after build
            cleanWs()
        }
    }
}
