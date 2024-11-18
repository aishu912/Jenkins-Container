pipeline{
  agent{
    label{
         label 'built-in'
         customWorkspace '/root/dockerCont/' 
    }
  }
  stages{
    stage('cleaning up existing containers'){
       steps{
            // Stop all running containers
            sh "docker stop \$(docker ps -q)"
            // Remove all containers (including stopped ones)
            sh "docker rm \$(docker ps -a -q)"
       }
    }
    stage('create a container'){
       steps{
         sh "docker run -d -p 80:80 --name contMaster httpd"
         
       }
    }
    
    stage('deploy'){
       steps{
         sh "docker cp index.html contMaster:/usr/local/apache2/htdocs"
         sh "docker exec contMaster chmod 755 /usr/local/apache2/htdocs/index.html"
       }
    }
  }
}
/*pipeline{
  agent{
    label{
         label 'built-in'
         customWorkspace '/root/dockerCont/' 
    }
  }
  stages{
    stage('cleaning up existing containers'){
      parallel{
        stage('master-cont'){
            steps{
                  // Stop all running containers
                  sh "docker stop \$(docker ps -q)"
                  // Remove all containers (including stopped ones)
                  sh "docker rm \$(docker ps -a -q)"
                  sh "docker run -d -p 80:80 --name contMaster httpd"
                  sh "docker cp index.html contMaster:/usr/local/apache2/htdocs"
                  sh "docker exec contMaster chmod 755 /usr/local/apache2/htdocs/index.html"
          }
        }
        stage('2025Q1'){
            steps{
                  // Stop all running containers
                  sh "docker stop \$(docker ps -q)"
                  // Remove all containers (including stopped ones)
                  sh "docker rm \$(docker ps -a -q)"
                  sh "docker run -d -p 8000:80 --name 2025Q1 httpd"
                  sh "docker cp index.html 2025Q1:/usr/local/apache2/htdocs"
                  sh "docker exec 2025Q1 chmod 755 /usr/local/apache2/htdocs/index.html"
          }
        }
        stage('2025Q2'){
            steps{
                  // Stop all running containers
                  sh "docker stop \$(docker ps -q)"
                  // Remove all containers (including stopped ones)
                  sh "docker rm \$(docker ps -a -q)"
                  sh "docker run -d -p 9090:80 --name 2025Q2 httpd"
                  sh "docker cp index.html 2025Q2:/usr/local/apache2/htdocs"
                  sh "docker exec 2025Q2 chmod 755 /usr/local/apache2/htdocs/index.html"
          }
        }
        stage('2025Q3'){
            steps{
                  // Stop all running containers
                  sh "docker stop \$(docker ps -q)"
                  // Remove all containers (including stopped ones)
                  sh "docker rm \$(docker ps -a -q)"
                  sh "docker run -d -p 8081:80 --name 2025Q3 httpd"
                  sh "docker cp index.html 2025Q3:/usr/local/apache2/htdocs"
                  sh "docker exec 2025Q3 chmod 755 /usr/local/apache2/htdocs/index.html"
          }
        }
      }
  }
}
}
*/
