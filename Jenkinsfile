pipeline{
    agent any
    stages{
        stage('checkout'){
            steps{
                echo 'docker repo'
                git url:' '     
                branch:'master' 
            }
        }
        stage('build'){
            steps{
                echo 'building docker image'
                bat 'docker build -t mywebapp .'
            }
        }
        stage('run'){
            steps{
                echo 'running docker image'
                bat 'docker rm -f mycontainer || exit 0'
                bat 'docker run -d -p 5000:5000 --name mycontainer mywebapp'
            }
        }
        post{
            success{
                echo 'pipeline successful'
            }
            failure{
                echo 'pipeline failed'
            }
            
        }
    }
}