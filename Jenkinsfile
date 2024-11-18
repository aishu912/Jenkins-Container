pipeline{
  agent{
    label 'built-in'
    customWorkspace '/root/dockerCont/'
  }
  stages{
    stage('master-cont'){
       steps{
         sh "docker run -itdp 80:80 --name contMaster httpd"
         
       }
    }
  }
}
