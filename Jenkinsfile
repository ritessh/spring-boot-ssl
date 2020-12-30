pipeline {
    agent any 
    stages {

        stage('Build') { 
            when {
                branch "develop"
            }
            steps {
                sh "/opt/apache-maven-3.6.3/bin/mvn clean package"
            }
        }
 //       stage('Test') { 
 //           steps {
 //               // 
 //           }
 //       }
 //       stage('Deploy') { 
 //           steps {
 //               // 
 //           }
 //       }
    }
}
