pipeline {
    agent {
        label {
            label "built-in"
            customWorkspace /mnt/cloneProject
        }
    }
    stages {
        stage ("cloning the git 23Q1 branch"){
            steps {
                rm -rf *
                git clone https://github.com/snehaos20/assignment1.git -b 23Q1
                echo "cloning successful"
                chmod -R 777 /mnt/cloneProject
            }
        }
        stage("craeting container"){
            docker container rm 23Q1 -f
            docker run --name 23Q1server -p 80:80 -d httpd
            docker cp /mnt/cloneProject/assigment1/index.html 23Q1server:/usr/local/apache2/htdocs
        }
    }
}
