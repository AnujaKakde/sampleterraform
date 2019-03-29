pipeline {
    agent {
        node {
            label 'master'
        }
    }

    stages {

        stage('terraform started') {
            steps {
                sh 'echo "Started...!" '
            }
        }
        stage('git clone') {
            steps {
                sh 'sudo rm -r *;sudo git clone https://github.com/AnujaKakde/sampleterraform.git'
            }
        }
        stage('tfsvars create'){
            steps {
                sh 'sudo cp /home/ec2-user/vars.tf ${WORKSPACE}'
            }
        }
        stage('terraform init') {
            steps {
                sh 'sudo /home/ec2-user/terraform init ${WORKSPACE}'
            }
        }
        stage('terraform plan') {
            steps {
                sh 'ls ./jenkins; sudo /home/ec2-user/terraform plan ${WORKSPACE}'
            }
        }
        stage('terraform ended') {
            steps {
                sh 'echo "Ended....!!"'
            }
        }

        
    }
}
