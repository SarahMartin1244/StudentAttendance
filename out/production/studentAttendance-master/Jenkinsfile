pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Clean workspace before fetching
                    deleteDir()

                    git 'https://github.com/SarahMartin1244/StudentAttendance.git'

                    // Building project using Maven
                    sh 'mvn clean install'
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
