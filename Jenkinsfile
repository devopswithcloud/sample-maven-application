pipeline {
    agent any
    stages {
        stage('Example Deploy') {
            when {
                //buildingTag()
                tag "release-*"
            }
            steps {
                echo 'Deploying'
            }
        }
    }
}
