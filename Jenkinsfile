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
         sh "docker chmod -R 755 contMaster:/usr/local/apache2/htdocs"
       }
    }
  }
}
