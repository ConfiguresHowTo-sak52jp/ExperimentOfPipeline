pipeline{
    agent{
        label 'built-in'
    }
    stages{
        stage("Parallel sleeping"){
            parallel{
                stage("Sleeping on 1st slave"){
                    steps{
                        build job: 'SlaveSleeper1'
                    }
                }
                stage("Sleeping on 2nd slave"){
                    steps{
                        build job: 'SlaveSleeper2'
                    }
                }
            }
        }
        stage("Final actions"){
            steps{
                build job: 'MainSleeper1'                
            }
        }
    }
}