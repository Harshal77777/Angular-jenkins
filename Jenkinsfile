pipeline {
    agent any
    tools { nodejs "NODEJS" }

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Angular App') {
            steps {
                sh 'npm run build -- --configuration production'
            }
        }

        stage('Serve Angular App') {
            steps {
                sh 'nohup npm run start -- --host 0.0.0.0 --port 4200 &'
            }
        }
    }
}
