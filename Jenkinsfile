library('coopdigital-pipelines-library')

pipeline{
    agent any

    stages {
        stage('pre-build'){
            steps{
                git (
                        branch: 'j11-fix',
                        url: 'https://github.com/coopdigital/audit4j-core.git'
                    )
                    sh "switch_to_java 8"
                }
        }

        stage('build-and-test'){
            steps {
                sh "mvn -B -U clean test"
            }
        }

        stage('deploy'){
            steps{
                sh 'mvn deploy'
            }
        }
    }

}