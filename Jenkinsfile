// Deakin Uni
pipeline {
    agent any

    stages {
        // Stage 1: Build
        stage('Build') {
            steps {
                echo 'Building the application...'
                // Example build tool: Maven or Gradle. Example: `sh 'mvn clean install'`
                echo 'Using Maven to compile and package the code.'
            }
        }

        // Stage 2: Unit and Integration Tests
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests...'
                // Example: `sh 'mvn test'`
                echo 'Running integration tests...'
                // Use tools like Selenium or Cucumber for integration testing.
            }
        }

        // Stage 3: Code Analysis
        stage('Code Analysis') {
            steps {
                echo 'Performing static code analysis...'
                // Example: SonarQube, Checkstyle. `sh 'sonar-scanner'`
                echo 'Code quality analysis done using SonarQube.'
            }
        }

        // Stage 4: Security Scan
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Use OWASP Dependency Check or Snyk. Example: `sh 'dependency-check'`
                echo 'Security scan completed using OWASP Dependency Check.'
            }
        }

        // Stage 5: Deploy to Staging
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to the staging environment...'
                // Example: AWS CLI, Terraform, or Ansible. `sh 'aws deploy ...'`
                echo 'Application deployed to staging server.'
            }
        }

        // Stage 6: Integration Tests on Staging
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on the staging environment...'
                // Run integration tests again on the staging server.
                echo 'Integration tests completed on staging.'
            }
        }

        // Stage 7: Deploy to Production
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to the production environment...'
                // Example: AWS CLI, Terraform, or Ansible. `sh 'aws deploy ...'`
                echo 'Application deployed to production server.'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }

        success {
            echo 'Pipeline succeeded. Sending success notification...'
            emailext subject: "Jenkins Pipeline: SUCCESS",
                body: "The Jenkins pipeline completed successfully. ${STAGE_NAME}",
                attachLog: true,
                to: 'sashenjayathilaka95@gmail.com'
        }

        failure {
            echo 'Pipeline failed. Sending failure notification...'
            emailext subject: "Jenkins Pipeline: FAILURE",
                body: "The Jenkins pipeline failed during the ${STAGE_NAME} stage. Check the logs for more details.",
                attachLog: true,
                to: 'sashenjayathilaka95@gmail.com'
        }
    }
}
