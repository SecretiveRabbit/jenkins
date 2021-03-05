pipeline {
    agent any
    
    environment {
        OWNER_NAME = "Alexander Stepanov"
        PROJECT_NAME = "Jenkinsfile"
    }

    stages {
        stage('the-first-stage') {
            steps {
                echo "Start of Stage Build"
                echo "Building......."
                echo "End of Stage Build"
                
            }
        }
        stage('the-second-stage') {
           steps { 
                echo "Start of Stage Test"
                echo "Testing......."
                sh '''
                echo "The name of the project is: ${PROJECT_NAME}."
                echo "And the owner of the project is ${OWNER_NAME}."
                echo "End of Stage Test"
                '''
           }
           }
         stage('the-third-stage') {
             steps {
                echo "Start of Stage Deploy"
                echo "Deploying......."
                sh '''
                touch file152
                rm file152
                '''
                echo "End of Stage Deploy"
             }
        }
    }
}
