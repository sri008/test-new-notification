// @Library('shareLibraries@main')_
// passVariable{infra = false}
// // cronJob{infra = false}
// @Library('shareLibraries@build-dependency')_
// subModule{}
pipeline{
    agent any
    stages {
        stage('build'){
            steps{
                sh 'npm pack'
                sh 'ls -l'
            }
        }
        stage('Push to main repo'){
            steps{
                script{
                    // Load the shared library from a specific branch using the BRANCH_NAME variable
                    library "shareLibraries@build-dependency"

                    // Call the function from the shared library
                    shareLibraries.subModule()
                }
            }
        }
    }
}