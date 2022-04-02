pipeline {

    agent any



    stages {

        stage('Build') {

            steps {

                sh """

                echo 'Building..'

                docker build -t bgstahl/project2:latest .

                docker login -u "bgstahl" -p "2wsx#EDC4rfv" docker.io

                docker push bgstahl/project2:latest

                """

            }

        }

        stage('Creating Docker Container') {

            steps {

                sh """

                echo 'Creating Docker Container...'

                pip install docker-compose

                chmod +x /var/lib/jenkins/.local/bin/docker-compose

                /var/lib/jenkins/.local/bin/docker-compose up -d --remove-orphans

                docker ps -a

               """

            }     

        }

    }

}
