pipeline{
    agent{
        label "Agent-1"
    }
    options{        
        // Timeout counter starts before agent is allocated
        timeout(time: 10, unit: "MINUTES")
        disableConcurrentBuilds()
    }
    parameters{
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    environment{
        DEPLOY_TO = "Production"
        GREETING = "GOOD MORNING"
    }
    stages{
        stage("build"){
            steps{
                sh "echo this is bulid"
                sh "env"
            }
            
        }
        stage("Test"){
            steps{
                sh "echo this is bulid"
            }
            
        }
        stage("deploy"){
            steps{
                sh "echo this is deploy"
                sh "echo test the webhook trigger"
            }
        }
        stage("parameters"){
            steps {
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
            }
        }
    }
    post{
        always{
            echo "this will run always"
        }
        success{
            echo "this will run only if build success"
        }
        failure{
            echo "this will run only if build fails"
        }
    }
}