pipeline {
    agent { label 'docker-agent' }

    environment {
        DOCKER_IMAGE = "my-repo/my-app"
        FULL_IMAGE = "${DOCKER_IMAGE}:${GIT_COMMIT}"
    }

    stages {
        stage('Unit Test') {
            steps {
                script {
                    runUnitTest()
                }
            }
        }

        stage('Build JAR') {
            steps {
                script {
                    buildJar()
                }
            }
        }

        stage('Build Image') {
            steps {
                script {
                    buildImage()
                }
            }
        }

        stage('Push Image') {
            steps {
                script {
                    pushImage()
                }
            }
        }

        stage('Delete Image Locally') {
            steps {
                script {
                    deleteImage()
                }
            }
        }

        stage('Update Manifests') {
            steps {
                script {
                    updateManifests()
                }
            }
        }

        stage('Push Manifests') {
            steps {
                script {
                    pushManifests()
                }
            }
        }
    }
}

