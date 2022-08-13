pipeline{
    agent any 

    stages{
        stage("test"){
            steps{
                echo "========executing test========"
                
               
            }
           
        }
        stage("build"){
            steps{
                echo "========executing build========"
                sh 'docker build -t shiva9921/hello-world-python:0.0.2.RELEASE  .'
                sh 'docker push shiva9921/hello-world-python:0.0.2.RELEASE'
                
           }
           
        }

          stage("deploy"){
            steps{
                echo "========executing build========"
                sh 'docker run -p 5000:5000  shiva9921/hello-world-python:0.0.2.RELEASE'
                sh 'docker ps'
            }
           
        }
    }
    post{
        
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}