// @Library('shareLibraries@main')_
// passVariable{infra = false}
// // cronJob{infra = false}
// @Library('shareLibraries@build-dependency')
// subModule{}
@Library('shareLibraries@build-dependency')

pipeline {
    agent any
    stages {
        stage('build') {
            steps{
                sh 'npm pack'
                sh 'ls -l'
            }
        }
        stage('Push to main repo') {
            steps {
                script {
                    subModule()
                }
            }
        }
    }
}