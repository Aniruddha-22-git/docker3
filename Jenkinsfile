pipeline{
  agent {
    label('slave1')
  }
  stages{
    stage('slave-vol'){
      steps{
        sh "sudo git clone https://github.com/Aniruddha-22-git/docker3.git -b 23q3 /mnt/23q3-vol"
        sh "sudo docker run -itdp 8083:80 -v /mnt/23q3-vol:/usr/local/apache2/htdocs --name 23q3-vol httpd"
        sh "sudo docker exec 23q3-vol chmod -R 777 /usr/local/apache2/htdocs"
      }
    }
  }
}
