pipeline{
  agent {
    label('slave1')
  }
  stages{
    stage('slave-vol'){
      steps{
         sh "sudo git clone https://github.com/Aniruddha-22-git/docker3.git -b 23q2 /mnt/23q2-vol"
        sh "sudo docker run -itdp 92:80 -v /mnt/23q2-vol:/usr/local/apache2/htdocs --name 23q2-vol httpd"
        sh "sudo docker exec 23q2-vol chmod -R 777 /usr/local/apache2/htdocs"
      }
    }
  }
}
