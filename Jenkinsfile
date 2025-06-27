pipeline {
    agent any

    stages {
        stage('Restore') {
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet build --configuration Release'
            }
        }
        stage('Publish') {
            steps {
                sh 'dotnet publish -c Release -o publish'
            }
        }
        stage('Deploy') {
            steps {
                sh 'cp -r publish/* /Users/phong/Desktop/deploy-folder'
            }
        }
    }

    post {
        success {
            echo '✅ CI/CD hoàn tất!'
        }
        failure {
            echo '❌ Có lỗi khi build/deploy.'
        }
    }
}
