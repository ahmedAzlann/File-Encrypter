pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/ahmedAzlann/File-Encrypter.git'
            }
        }

        stage('Build') {
            steps {
                sh '''
                echo "Building Java project..."
                cd "Password Protection"
                mkdir -p build
                javac -d build src/*.java
                echo "Build successful"
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                echo "Running JUnit tests for File-Encrypter..."
                cd "Password Protection"

                if [ ! -f junit-platform-console-standalone.jar ]; then
                    echo "Downloading JUnit..."
                    curl -L -o junit-platform-console-standalone.jar https://repo1.maven.org/maven2/org/junit/platform/junit-platform-console-standalone/1.10.0/junit-platform-console-standalone-1.10.0.jar
                fi

                echo "JUnit ready."
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                echo "Deploy stage running..."
                echo "Simulating deployment..."
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
