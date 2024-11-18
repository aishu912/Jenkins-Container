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
         sh "docker run -d -p 80:80 --name contMaster1 httpd"
         sh "docker cp index.html contMaster1:/usr/local/apache2/htdocs"
       }
    }
  }
}
