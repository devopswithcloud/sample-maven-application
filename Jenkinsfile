pipeline {
    agent any
    stages {
        stage('Example Deploy') {
            when {
                changeRequest()
            }
            steps {
                echo 'Deploying through PR'
            }
        }
    }
}
