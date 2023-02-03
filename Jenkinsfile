pipeline {
    agent { label 'OPEN'}
     stages {
        stage('Clone Git Repository') {
            steps {
                git url: 'https://github.com/instinct1one/angular-realworld-example-app.git',
				branch: 'master'
            }
        }
        stage('@angular/cli') {
            steps {
                sh 'sudo npm install -g @angular/cli'
            }
        }
        stage('npm dependencies') {
            steps {
                sh 'sudo npm install --global --force yarn'
            }
        }
        stage('yarn dependencies') {
            steps {
                sh 'yarn install'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'ng build --prod'
            }
        }
        stage('serve') {
            steps {
                sh 'ng serve'
            }
        }
    }
}
