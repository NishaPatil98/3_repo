pipeline {
agent {
label {
label "built-in"
customWorkspace "/mnt/branches"

}
}
environment {
devip = "172.31.36.195"
}
stages {
stage("clone"){
steps {
sh "git clone https://github.com/NishaPatil98/3_repo.git"

}
}
stage("copy-in-dev") {

steps {
sh "sudo yum install httpd -y"
sh "service httpd start"
sh "scp -R /mnt/branches/3_repo nisha@${devip}:/var/www/html/"
} 
}
}
}
