pipeline{
  agent{
    label{
         label 'built-in'
         customWorkspace '/root/dockerCont/' 
    }
  }
  stages{
    stage('cleaning up existing containers'){
       /*steps{
            // Stop all running containers
            sh "docker stop \$(docker ps -q)"
            // Remove all containers (including stopped ones)
            sh "docker rm \$(docker ps -a -q)"
       }
    }
    stage('create a container'){
       steps{
         sh "docker run -d -p 9090:80 --name 2025Q2 httpd"
         git branch: '2025Q2', changelog: false, poll: false, url:'https://github.com/aishu912/Jenkins-Container.git'
       }
    }
    
    stage('deploy'){
       steps{
         sh "docker cp index.html 2025Q2:/usr/local/apache2/htdocs"
         sh "docker exec 2025Q2 chmod 755 /usr/local/apache2/htdocs/index.html"
       }
    }*/
  }
}
}
