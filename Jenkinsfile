pipeline {
agent {
label {
label "built-in"
customWorkspace "/mnt/branches"

}
}
environment {
qaip = "172.31.6.127"
}
stages {
stage("clone"){
steps {
  sh "rm -rf *"
sh "git clone https://github.com/NishaPatil98/3_repo.git"

}
}
stage("install") {
  agent {
    label {
    label "qa"
      customWorkspace "/mnt/branches"
    }
  }
steps {
sh "sudo yum install httpd -y"
sh "sudo service httpd start"

} 
}
  stage ("copy-to qa"){
    steps {
      steps {
      sh "scp -r /mnt/branches/3_repo nisha@${qaip}:/var/www/html/"
      }
    }
  }
}
}
