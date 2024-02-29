pipeline {
    agent any

    // tools {
    //     // Specify the JDK and Android SDK tools you have configured in Jenkins Global Tool Configuration
    //     jdk 'JDK_Name'
    // }

    environment {
        // Set the path for the Android SDK, which might be needed for your builds
        ANDROID_HOME = "${tools.androidSdk}"
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout your source code from version control system e.g., Git
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Build your Android app with Gradle Wrapper
                // You might need to adjust the gradle command according to your project structure and build script
                sh './gradlew assembleDebug'
            }
        }

    }

    post {
        // Define post-build actions such as cleanup, notifications, etc.
        success {
            // Actions to take on successful build
            echo 'Build was successful.'
        }
        failure {
            // Actions to take if the build fails
            echo 'Build failed.'
        }
    }
}
