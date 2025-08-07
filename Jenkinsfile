pipeline {
    agent any
    tools {
        maven 'maven'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                    echo "Stopping existing Spring Boot application..."
                    sudo pkill -f spring_app_sak-0.0.1-SNAPSHOT.jar

                    echo "Starting the Spring application..."
                    sudo java -jar target/spring_app_sak-0.0.1-SNAPSHOT.jar > /dev/null 2>&1 &
                '''
            }
        }
    }
    post {
        success {
            echo "Deployed successfully"
        }
        failure {
            echo "Failed to Deploy"
        }
    }
}
