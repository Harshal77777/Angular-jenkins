pipeline {
    agent any
    tools { nodejs "NODEJS" }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Harshal77777/Angular-jenkins.git'
            }
        }

        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Deliver') {
            steps {
                sh 'chmod +x ./Jenkins/Scripts/deliver.sh'
                sh 'chmod +x ./Jenkins/Scripts/kill.sh'
                sh './Jenkins/Scripts/deliver.sh'
            }
        }

        stage('Approval') {
            steps {
                input message: "Finished using the website? Click 'Proceed' to continue."
            }
        }

        stage('Cleanup') {
            steps {
                sh './Jenkins/Scripts/kill.sh'
            }
        }
    }
}
