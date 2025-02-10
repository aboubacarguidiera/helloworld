pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M398"
    }
    stages {
        stage("Echo Version") {
            steps {
                sh 'echo "Print Maven Version"'
                sh 'mvn -version'
            }
        }
        stage("Build") {
            steps {
                // Clone the repository
                //git branch: 'main', changelog: false, poll: false, url: 'http://139.84.159.194:5555/dasher-org/jenkins-hello-world.git'

                // Run Maven commands
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage("Unit Tests") {
            steps {
                sh 'mvn test'
            }
        }
    }
}
