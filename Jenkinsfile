pipeline {
    agent any
    stages {
        stage('Example Deploy') {
            when {
              // changelog '.*some_text.*'
                changelog 'lgtm'
            }
            steps {
                echo 'Deploying with new word'
            }
        }
    }
}
