pipeline{
    agent any
  tools {
    maven 'maven'
  }
    stages {
        stage('Build'){
            steps{
                sh "mvn clean package"
            }
        }
        
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: '58fb1fd6-0e22-455d-8f67-503f0fd6c433', path: '', url: 'http://ec2-34-229-14-180.compute-1.amazonaws.com:8080/')], contextPath: '/hello', war: '**/HelloJenkins.war'
            }
        }
    }
}
