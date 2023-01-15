pipeline {
    agent any
    environment {
        DEPLOY_TO = 'productions' //changed here 
        // BRANCH_NAME = env.BRANCH_NAME
    }
    stages {
        stage('Example Build') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Example Deploy') {
            when {
                allOf {
                    expression { BRANCH_NAME ==~ /(production|staging)/ }
                    //branch 'production'
                    environment name: 'DEPLOY_TO', value: 'production'
                }
            }
            steps {
                echo 'Deploying'
            }
        }
    }
}
