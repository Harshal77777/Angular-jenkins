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

        stage('Serve Angular App') {
            steps {
                sh '''
                if [ ! -d "dist/my-angular-app" ]; then
                    echo "Error: Build directory not found! Please run 'ng build' locally first."
                    exit 1
                fi
                nohup npx serve -s dist/my-angular-app -l 4200 &
                '''
            }
        }
    }
}
