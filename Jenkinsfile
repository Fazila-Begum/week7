pipeline{
  agent any
          stages{
              stage('Build'){
                  step{
                      echo "Build Docker Image"
                      bat "docker build -t myapp"
                }
            }
    stage('Run'){
      steps{
        echo "Run application in dockercontainer"
        bat "docker run -f mycontainer || exit 0"
        bat "docker run -d -p 5000:5000 --name mycontainer my app"
          }
        }
      }
post{
  success{
        echo"pipeline completed successfully"
        }
  failure{
      echo "pipeline failed"
    }
  }
}
