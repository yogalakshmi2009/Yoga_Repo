pipeline {
    agent none
    stages{
        stage('Non parallel stage'){
            agent{
                label "master"
            }
            steps{
                echo "This will be executed first"
            }
        }
        stage('Run tests'){
            parallel{
                stage('Test on windows'){
                 agent{
                label "Windows_Node"
                    }
                steps{
                    echo "Task1 on Agent"
                    }
                }
               stage('Test on master'){
                   agent{
                       label "master"
                   }
                   steps{
                       echo "Task1 on Master"
                   }
               }
            
            }
        }
    }
}
