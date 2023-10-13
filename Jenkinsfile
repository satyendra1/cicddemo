node('workernode') {
    stage('Source') {
        checkout scm
    }
    stage('Build') {
        // Execute gradle build associated with this project.
        sh 'chmod +x gradlew'
        sh './gradlew build'
    }
    stage('DockerBuild') {
        sh "docker image build -t $JOB_NAME:$BUILD_ID"
    }
}
