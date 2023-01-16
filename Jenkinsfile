@Library("pipeline-shared-lib") _
pipeline {
    agent any
    tools {
        maven 'Existing_MVN'
    }
    stages {
        stage('checkoutCode'){
            steps {
                // Checkout code from github repo
                git credentialsId: 'devopswithcloud_git_creds', url: 'https://github.com/devopswithcloud/sample-maven-application.git'
            }
        }
        stage('version') {
            steps {
                build("version")
            }
        }
    }
}
