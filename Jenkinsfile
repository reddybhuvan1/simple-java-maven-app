node {
        stage('SCM') {
                echo 'Fetching the code'
                git changelog: false, poll: false, url: 'https://github.com/TechWithKhanam/simple-java-maven-app.git'
            }
        stage('BUILD') {
                echo 'Building the project'
                bat 'mvn clean install'
            }
        stage('TEST') {
                echo 'Testing the project'
                bat 'mvn test'
            }
        stage('VERIFY DOCKERFILE') {
                echo 'Verifying Dockerfile presence'
                bat 'dir'
            }
        stage('DEPLOY') {
                echo 'Deploying the project in Docker container'
                script {
                    // Check if Docker is running and available
                    bat 'docker --version'
                    
                    // Build the Docker image
                    bat 'docker build -t myapp1:latest .'
                    
                    // Run the Docker container
                    bat 'docker run -d -p 9090:8080 --name myapp2_container myapp1:latest'
                }
            }
    }
