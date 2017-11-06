pipeline {
    agent {
            label "10.157.109.48"
          } 
    tools {
        maven 'Maven3.1.1'
        jdk 'java8'
    }
    stages {
        stage ('Initialize') {
            steps {
                bat '''
                    echo "PATH = %PATH%"
                    echo "JAVA_HOME = %JAVA_HOME%"
                    echo "M2_HOME = %M2_HOME%"
                '''
            }
        }

        stage ('Build') {
            steps {
                bat 'set JAVA_HOME=C:\Jenkins\tools\hudson.model.JDK\java8'
                bat 'echo "JAVA_HOME = %JAVA_HOME%"'
                bat 'cd NumberGenerator & mvn install'
            }
             post {
                success {
                    junit 'NumberGenerator/target/surefire-reports/*.xml'
                        }
                 }
               

           
            }
        }
    
}
