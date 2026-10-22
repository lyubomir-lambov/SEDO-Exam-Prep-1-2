
pipeline {
    agent any

    tools {
        dotnetsdk 'dotnet6'
    }

    stages {
        stage('Restore') {
            steps {
                sh 'dotnet restore SoftUniBazar.sln'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build SoftUniBazar.sln --no-restore'
            }
        }

        stage('Test') {
            steps {
                sh 'dotnet test SoftUniBazar.sln --no-build --verbosity normal'
            }
        }
    }
}
