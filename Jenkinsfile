pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        nodejs "my-nodejs"
    }

    stages {
        stage('Source Code Checkout') {
            steps {
                echo 'Angular Test Project GitHub Repository Code Checkout'
                // Get some code from a GitHub repository
                git 'https://github.com/swagat030/angular-test-code.git'
                
            }
        }
        stage('Install dependency') {
            steps {
                echo 'Angular Test Project npm Install'
                sh "npm install"
            }
        }
        // stage('Testing Stage') {
        //     steps {
        //         echo 'Angular Test Project Code Unit Testing Stage'
        //         sh 'npx ng test --no-watch --code-coverage'
        //     }
        // }
        // stage('Sonar Scanner Coverage') {
        //     steps {
        //         echo 'Angular Test Project Sonar Scanner Coverage'
        //         sh "npm run sonar"
        //     }
        // }
        stage('Make Prod Build') {
            steps {
                echo 'Angular Test Project Prod Build'
                sh 'npx ng build --prod --base-href=/angular-test-code/ && cd dist/angular-test-code && jar -cvf angular-test-code.war *'
            }
        }
       stage('Deploy Application with Tomcat Server' ) {
            steps {
                echo 'Angular Test Project Deployement with Tomcat Server'
            }
        }
    }
}