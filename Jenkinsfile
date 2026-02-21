pipeline{
    agent any
    stages{
        stage('Restore dependencies'){
            when{
                branch 'main'
            }
            steps{
                echo 'Restoring dependencies...'
                bat 'dotnet restore'
            }
        }
        stage('Build'){
            when{
                branch 'main'
            }
            steps{
                echo 'Building the application...'
                bat 'dotnet build --no-restore'
            }
        }
        stage('Test'){
            when{
                branch 'main'
            }
            steps{
                echo 'Running tests...'
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}