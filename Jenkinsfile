pipeline {
    agent {
        label {
            label "built-in"
            customWorkspace "/mnt/cloneProject"
        }
    }
    stages {
        stage("cloning 23Q2 branch"){
            steps {
                sh "rm -rf *"
                sh "git clone https://github.com/snehaos20/assignment1.git -b 23Q2"
                echo "cloning project"
                sh "chmod -R 777 /mnt/cloneProject"
            }
        }
        stage("creating 23Q2 container"){
            steps {
                sh "docker run --name 23Q2server -p 80:80 -d httpd"
                sh "docker cp /mnt/cloneProject/assignment2/index.html 23Q2server:/usr/local/apache2/htdocs"
            }
        }
    }
}
