pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    stages {
        stage('Example Build') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Example Deploy') {
            steps {
                echo 'New Deploying'
            }
        }
    }
}