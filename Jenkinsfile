pipeline{
  agent {
    label('slave1')
  }
  stages{
    stage('slave-vol'){
      steps{
        sh "sudo yum install docker -y"
        sh "sudo systemctl start docker"
        sh "sudo systemctl enable docker"
        sh "sudo git clone https://github.com/Aniruddha-22-git/docker3.git -b 23q1 /mnt/23q1-vol"
        sh "sudo docker run -itdp 82:80 -v /mnt/23q1-vol:/usr/local/apache2/htdocs --name 23q1-vol httpd"
        sh "sudo docker exec 23q1-vol chmod -R 777 /usr/local/apache2/htdocs"
      }
    }
  }
}
