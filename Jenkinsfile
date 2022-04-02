pipeline {
        agent any

        stages {
                stage('Build Docker Image') {
                        steps {
                                echo 'Building Docker Image'
                                docker build –t bgstahl/project2:latest .
                                docker login –u “bgstahl” -p “Lux2lumens” docker.io
                                docker push bgstahl/project2:latest
                        }
                }
	}
}
