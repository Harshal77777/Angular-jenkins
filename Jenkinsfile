pipeline {
    agent any
    tools { nodejs "NODEJS" }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'ng build --configuration production'
            }
        }
        stage('Serve') {
            steps {
                sh 'nohup ng serve --host 0.0.0.0 --port 4200 > ng.log 2>&1 &'
            }
        }
    }
}
