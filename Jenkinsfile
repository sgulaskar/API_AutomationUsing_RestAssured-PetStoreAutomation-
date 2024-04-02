pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the GitHub repository
                git 'https://github.com/sgulaskar/API_AutomationUsing_RestAssured-PetStoreAutomation-.git'
            }
        }

        stage('Build') {
            steps {
                // Use Maven to build the project
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                // Run tests if needed
                bat 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the artifact if needed
                // For example, deploy to a Maven repository
                bat 'mvn deploy'
            }
        }
    }

    post {
        success {
            // Send notifications or perform additional actions on success
            echo 'Build succeeded!'

            // For example, send an email notification
            emailext (
                to: 'thekingsangram@gmail.com',
                subject: 'Build Success',
                body: 'The build succeeded. Congrats!'
            )
        }

        failure {
            // Send notifications or perform additional actions on failure
            echo 'Build failed!'

            // For example, send an email notification
            emailext (
                to: 'thekingsangram@gmail.com',
                subject: 'Build Failure',
                body: 'The build failed. Please investigate!'
            )
        }
    }
}
