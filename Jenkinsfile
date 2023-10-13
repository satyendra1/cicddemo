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
        def customImage = docker.build("my-image:${env.BUILD_ID}")
        customImage.push()
        customImage.push('latest')
    }
}
