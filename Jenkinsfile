pipeline {
    parameters {
        choice(
            name: 'ENGINE',
            choices: [
                'ALL',
                'OCP',
                'PCP',
                'AZURE_PG',
                'AZURE_SQL',
                'PRIVATE_SUBSCRIPTION',
                'AZURE_SUBSCRIPTION'
            ],
            description: 'Run test for specific engine'
        )
    }
    agent any
    stages {
        stage('build') {
            steps {
                sh 'echo $ENGINE'
            }
        }
        stage('test OCP') {
            when { 
                anyOf {
                    expression { params.ENGINE == 'OCP' }
                    expression { params.ENGINE == 'ALL' }
                    expression { params.ENGINE == 'PRIVATE_SUBSCRIPTION' }
                }
            }
            steps{
                sh 'echo "This is test OCP"'
            }
        }
        stage('test PCP') {
            when{
                anyOf { 
                    expression { params.ENGINE == 'PCP' }
                    expression { params.ENGINE == 'ALL' }
                    expression { params.ENGINE == 'PRIVATE_SUBSCRIPTION' }
                }
            }
            steps{
                sh 'echo "This is test PCP"'
            }
        }
        stage('test AZURE_PG') {
            when{
                anyOf {
                    expression { params.ENGINE == 'AZURE_PG' }
                    expression { params.ENGINE == 'ALL' }
                    expression { params.ENGINE == 'AZURE_SUBSCRIPTION' }
                }
            }
            steps{
                sh 'echo "This is test AZURE_PG"'
            }
        }
        stage('test AZURE_SQL') {
            when{
                anyOf {
                    expression { params.ENGINE == 'AZURE_SQL' }
                    expression { params.ENGINE == 'ALL' }
                    expression { params.ENGINE == 'AZURE_SUBSCRIPTION' }
                }
            }
            steps{
                sh 'echo "This is test AZURE_SQL"'
            }
        }
    }
}