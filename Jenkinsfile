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
		sh "docker build -t springboot-demo-secure-prometheus:${GIT_COMMIT} ./"
		sh "docker tag springboot-demo-secure-prometheus:${GIT_COMMIT} docker-registry:5000/springboot-demo-secure-prometheus:latest"
		sh "docker push docker-registry:5000/springboot-demo-secure-prometheus:latest"
            }
        }
 //       stage('Deploy') { 
 //           steps {
 //               // 
 //           }
 //       }
    }
}
