pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/jjmarkcosta/MySpringBootApp.git'

                // Run Maven on a Unix agent.
                bat "mvn compile"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
        stage('Test') {
            steps {
                // Run Maven on a Unix agent.
                bat "mvn test"
                
                echo 'Testing the Project with Maven Test'
            }
        }
        stage('Deploy') {
            steps {
                // Run Maven on a Unix agent.
                bat "mvn package"
                
                echo 'Deploying the Project with Maven Package'
            }
        }
    }
}
