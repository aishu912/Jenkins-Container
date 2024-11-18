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
            sh "docker run -d -p 8081:80 --name 2025Q1 httpd"
            sh "docker cp index.html 2025Q1:/usr/local/apache2/htdocs"
            sh "docker exec 2025Q1 chmod 755 /usr/local/apache2/htdocs/index.html"
       
       }
  }
}
}
