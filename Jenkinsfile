pipeline{
  agent{
    label 'built-in'
    customWorkspace '/root/dockerCont/'
  }
  stages{
    stage('master-cont'){
       steps{
         sh "docker run -d -p 80:80 --name contMaster httpd"
       }
    }
  }
}
