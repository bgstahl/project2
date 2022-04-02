pipeline {
	agent any

	stages {
		stage('Build Docker Image') {
			steps {
				sh “””
					echo 'Building Docker Image'
					docker build –t bgstahl/project2:latest .
					docker login –u “bgstahl” -p “Lux2lumens” docker.io
					docker push bgstahl/project2:latest
				“””
			}
		}
		stage('Create Docker Container') {
			steps {
				sh “””                
					echo 'Creating Docker Container'
					pip install docker-compose
					chmod +x /var/lib/Jenkins/.local/bin/docker-compose
					/var/lib/Jenkins/.local/bin/docker-compose up –d –remove-orphans
					docker ps –a
				“””
			}
		}
	}
}
