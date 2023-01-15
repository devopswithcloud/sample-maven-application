pipeline {
    agent any 
    tools {
        maven 'MVN_NEW_3.8.7'
    }
    options {
        buildDiscarder logRotator(numToKeepStr: '5')
        timestamps()
    }
    /*triggers {
        pollSCM '* * * * *'
        cron '* * * * *'
    }*/
    stages {
        stage('checkoutCode'){
            steps {
                // Checkout code from github repo
                git credentialsId: 'devopswithcloud_git_creds', url: 'https://github.com/devopswithcloud/sample-maven-application.git'
            }
        }
        stage('Build'){
            steps {
            // to perform build
            sh 'mvn clean package'
           /* sh '''export MAVEN_HOME=/opt/apache-maven-3.8.7
                PATH=$PATH:$HOME/bin:$MAVEN_HOME/bin
                mvn clean package
            '''*/

            }
        }
        stage ('Sonar'){
            steps {
                // Performing Sonar Scan
                sh 'mvn sonar:sonar'
            }
        }
        stage ('UploadArtifact'){
            steps {
                // Upload artifact
                sh 'mvn deploy'
            }
        }
        stage ('Deploy To Dev Tomcat'){
            steps {
                // Deploying to dev enviornment in Tomcat
                echo 'Hello tomcat'
            }
        }
    }
    post {
        always {
            // One or more steps need to be included within each condition's block.
            echo "I am Printing always, as i dont have any other work"
        }
        success {
            // One or more steps need to be included within each condition's block.
            echo "Yahoo!, job is success"
        }
        failure {
            // One or more steps need to be included within each condition's block.
            echo "OOPS!, Job failed. Its not my responsibility"
        }
    }
}
