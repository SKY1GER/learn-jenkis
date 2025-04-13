pipeline{
    agent{
        label "Agent-1"
    }
    options{        
        // Timeout counter starts before agent is allocated
        timeout(time: 30, unit: "MINUTES")
        disableConcurrentBuilds()
    }
    stages{
        stage("build"){
            steps{
                sh "echo this is bulid"
            }
            
        }
        stage("Test"){
            steps{
                sh "echo this is bulid"
                sh "sleep 10"
            }
            
        }
        stage("deploy"){
            steps{
                sh "echo this is deploy"
            }
        }
    }
}