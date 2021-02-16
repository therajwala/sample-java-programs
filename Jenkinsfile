pipeline {
    agent any
    stages {
        Stage (checkout) {checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/therajwala/sample-java-programs.git']]])}
        stage( clean') { 
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
