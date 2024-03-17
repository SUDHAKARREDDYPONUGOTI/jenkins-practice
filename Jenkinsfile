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

    // this job run in 1 seconds/hours , with in te limit not running it will exit
    options {
        timeout(time: 1, unit: 'HOURS') 
        disableConcurrentBuilds()      // it wont allow two builds at a Time - remove concurrence
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
        stage('Param Checking') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
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