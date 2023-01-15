pipeline {
    agent any
    stages {
        stage('Example Deploy') {
            when {
                buildingTag()
            }
            steps {
                echo 'Deploying'
            }
        }
    }
}
