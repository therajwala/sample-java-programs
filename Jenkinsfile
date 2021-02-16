pipeline {
    agent any
    stages {
        stage('clean') { 
            steps {
                withMaven {
      sh "mvn clean verify"
    }
    steps {
                sh '''sudo cp -Rf webapp/target/portal.war /usr/local/tomcat9/webapps/
  sudo systemctl restart tomcat'''
    }
    
            }
        }
    }
}
