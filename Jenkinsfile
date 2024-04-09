pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                dir('<your-project-folder>'){
                    sh 'docker run -t --rm -v "$(pwd)":/tmp/project katalonstudio/katalon katalonc.sh -projectPath=/tmp/project -browserType="Chrome" -retry=0 -statusDelay=15 -testSuitePath="Test Suites/Cura Healthcare" -apiKey=9b26b1f9-8b64-4c42-b5d9-1583bf3ae781'
                }
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'Reports/**/*.*', fingerprint: true
            junit 'Reports/**/JUnit_Report.xml'
        }
    }
}
