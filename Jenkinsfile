pipeline {
 agent any
 triggers {
  pollSCM('* * * * *')
 }

 stages {
  stage('Checkout'){
   git branch: 'main',
   url: 'https://github.com/zongs82-max/source-maven-java-spring-hello-webapp.git'
  }
 }

  stage('Build'){
   steps{
    sh 'mvn clean package'
   }
  }
  stage('Deploy'){
   steps{
    deploy adapters: [tomcat9(credintialsId: 'tomcat-manager', url:'http://192.168.56.102:8080')], contextPath: null, war: 'target/hello-world.war'
   }
  }


}
