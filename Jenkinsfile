pipeline {
    agent any
    
    stages {
        stage('Pull Docker Image') {
            steps {
                script {
                    docker.image('katalonstudio/katalon:latest').pull()
                }
            }
        }
        stage('Run Tests') {
            steps {
                script {
                   docker run -d -t --rm -v '/Users/gia/.jenkins/workspace/docker pipeline:/tmp/project' katalonstudio/katalon:latest katalonc.sh -projectPath=/tmp/project -browserType=Chrome -retry=0 -statusDelay=15 '-testSuitePath=Test Suites/Cura Healthcare' -apikey=9b26b1f9-8b64-4c42-b5d9-1583bf3ae781

                }
            }
        }
        // Add more stages as needed
    }
}
