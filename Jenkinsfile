pipeline {
    agent {
        label 'slave-2'
    }
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm			       
            }
        }
        stage('Build') {
            steps {
                sh '/home/node1/jenkins-node/apache-maven-3.9.6/bin/mvn install'
            }
        }
        stage('Deployment') {
            steps {
                // Copy the WAR file directly to the webapps directory
                sh 'cp target/slave-project.war /home/node1/jenkins-node/apache-tomcat-9.0.88/webapps'
                
                // Print a message indicating successful deployment
                echo "Deployment has been completed!"
            }
        }
    }
}

