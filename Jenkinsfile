pipeline {
    agent any
    tools { nodejs "NODEJS" }

    stages {
        stage('Install Angular CLI & Dependencies') {
            steps {
                sh 'npm install -g @angular/cli'   // Install Angular CLI globally
                sh 'npm install'                   // Install project dependencies
            }
        }

        stage('Build Angular App') {
            steps {
                sh 'ng build --configuration production'
            }
        }

        stage('Serve Angular App') {
            steps {
                sh 'nohup ng serve --host 0.0.0.0 --port 4200 &'
            }
        }
    }
}
