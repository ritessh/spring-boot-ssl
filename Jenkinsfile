pipeline {
    agent any 
    stages {

        stage('Build') { 
            when {
                branch "develop"
            }
            steps {
                sh "mvn clean package"
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
