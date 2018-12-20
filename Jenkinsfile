pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Checkout') { 
            steps {
                echo 'Checkout'
                sh '''
                    chmod +x ./jenkins/scripts/build.sh
                    ./jenkins/scripts/build.sh
                    '''
            }
        }

        stage('Build') { 
            steps {
                echo 'Build'
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}