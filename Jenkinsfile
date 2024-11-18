pipeline{
  agent{
    label{
         label 'built-in'
         customWorkspace '/root/dockerCont/' 
    }
  }
  stages{
    stage('master-cont'){
       steps{
         
         sh "docker run -d -p 80:80 --name contMaster httpd"
         sh "docker cp index.html contMaster:/usr/local/apache2/htdocs"
         sh "docker exec contMaster chmod 755 /usr/local/apache2/htdocs/index.html"
       }
    }
  }
}
