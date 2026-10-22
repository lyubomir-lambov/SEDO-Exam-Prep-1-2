
pipeline {
    agent any

    stages {
        stage('Restore') {
            when {
                anyOf {
                    branch 'feature'
                    branch 'main'
                }
            }
            steps {
                sh 'dotnet restore SoftUniBazar.sln'
            }
        }

        stage('Build') {
            when {
                anyOf {
                    branch 'feature'
                    branch 'main'
                }
            }
            steps {
                sh 'dotnet build SoftUniBazar.sln --no-restore'
            }
        }

        stage('Test') {
            when {
                anyOf {
                    branch 'feature'
                    branch 'main'
                }
            }
            steps {
                sh 'dotnet test SoftUniBazar.sln --no-build --verbosity normal'
            }
        }
    }
}
