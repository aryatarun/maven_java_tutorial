pipeline {
    agent {
            label "Windows"
          } 
    tools {
        maven 'Maven3.3.9'
        jdk 'java8'
    }
    stages {
        stage ('Initialize') {
            steps {
                bat 'set M2_HOME=C:\\opt\\Maven'
                bat '''
                    echo "PATH = %PATH%"
                    echo "JAVA_HOME = %JAVA_HOME%"
                    
                    echo "M2_HOME = %M2_HOME%"
                '''
            }
        }

        stage ('Build') {
            steps {
                
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
