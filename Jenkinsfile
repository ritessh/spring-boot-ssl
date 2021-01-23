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
        stage('Build Docker Image') { 
	    when {
		branch "develop"
		}
            steps {
		sh "/usr/local/bin/docker build -t springboot-demo-secure-prometheus:${GIT_COMMIT} ./"
		sh "/usr/local/bin/docker tag springboot-demo-secure-prometheus:${GIT_COMMIT} 192.168.225.14:5000/springboot-demo-secure-prometheus:latest"
		sh "/usr/local/bin/docker push 192.168.225.14:5000/springboot-demo-secure-prometheus:${GIT_COMMIT}"
            }
        }
 //       stage('Deploy') { 
 //           steps {
 //               // 
 //           }
 //       }
    }
}
