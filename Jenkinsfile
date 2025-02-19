pipeline {
    agent any
    tools { nodejs "NODEJS" }
    
    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/Harshal77777/Angular-jenkins.git'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        
        stage('Build Angular App') {
            steps {
                sh 'ng build --configuration production'
            }
        }

        stage('Serve Angular App') {
            steps {
                sh 'nohup npx serve -s dist/my-angular-app -l 4200 &'
            }
        }
    }
}
