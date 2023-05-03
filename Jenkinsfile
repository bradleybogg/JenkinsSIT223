 pipeline{
     agent any
     environment {
         DIRECTORY_PATH= "https://github.com/bradleybogg/JenkinsSIT223.git"
         TESTING_ENVIRONMENT= "Jenkins Git Integration"
         PRODUCTION_ENVIRONMENT= "Bradley Bogg"
     }
     stages {
         stage('Build Stage') {
             steps {
                 echo "Build code using Maven."
             }
         }
         stage('Unit Integration Test Stage') {
             steps {
                 echo "Running unit tests using JUnit"
                 echo "Running integration tests using Selenium"
                 echo "Tests Passed: ABCDEF"
             }
             post {
                always {
                    emailext(
                        subject: "Unit Test Email",
                        to: "boggbradley@gmail.com",
                        body: "Unit integration test was ${currentBuild.result}",
                        attachLog: true,
                    )
                    
                }
             }
         }
         stage('Code Analysis Stage') {
             steps {
                 echo "Integrating SonarQube for code analysis using Jenkins"
             }
         }
         stage('Security Scan Stage') {
             steps {
                 echo "Performing security scan using Veracode"
             }
             post {
                always {
                    emailext(
                        subject: "Security Email",
                        to: "boggbradley@gmail.com",
                        body: "Security stage was ${currentBuild.result}",
                        attachLog: true,
                    )
                    
                }
             }
         }
         stage('Deploy to Staging Stage') {
             steps {
                 echo "Deploying the application to a staging server using AWS CLI, EC2"
             }
         }
         stage('Integration Test on Staging Stage') {
             steps {
                 echo "Running integration tests on the staging environment using Jenkins"
             }
         }
         stage('Deploy to Production Stage') {
             steps {
                 echo "Deploying the application to a production server using AWS ECS"
             }
         }
    }

 }
