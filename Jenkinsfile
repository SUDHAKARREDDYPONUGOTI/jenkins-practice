pipeline {
    //agent adds bassed on the label name
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment { 
        GREETING = 'Jenkins'
    }
    //build-- 
    stages {
        stage('Example Build') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Example Deploy') {
            steps {
                sh """
                    echo "hello shell script"
                    echo '$GREETING'

                """
            }
        }
    }
    // post build -- 
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        // this runs when failures 
        failure { 
            echo 'this runs when build failures say Hello again!'
        }
        // this is success
        success { 
            echo 'this runs when build failures say Hello again!'
        }
    }

}