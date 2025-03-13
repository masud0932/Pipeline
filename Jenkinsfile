pipeline {
    agent any

    tools {
        maven 'Maven'  // Make sure "Maven" is configured in Jenkins settings
    }

    environment {
        M2_HOME = tool 'Maven' // Explicitly set Maven home
        PATH = "${M2_HOME}/bin:${env.PATH}" // Ensure Maven is available in the path
    }

    stages {
        stage('Initialize') {
            steps {
                sh '''
                echo "PATH = $PATH"
                echo "M2_HOME = $M2_HOME"
                mvn -version
                '''
            }
        }

        stage('Build with Maven') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
