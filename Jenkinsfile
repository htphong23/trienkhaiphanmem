pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/htphong23/trienkhaiphanmem.git'
            }
        }
        stage('Restore') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                bat 'dotnet build -c Release'
            }
        }
        stage('Publish') {
            steps {
                bat 'dotnet publish -c Release -o publish'
            }
        }
        stage('Deploy') {
            steps {
                bat 'xcopy /s /y publish\\* "C:\\inetpub\\wwwroot\\food-ordering"'
            }
        }
    }
}
