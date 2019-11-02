node('master')
{
  stage('Continuous Download') 
  {
    git 'https://github.com/intelliqittrainings/maven.git'
  } 
  stage('Continuous Build')
  {
      sh label: '', script: 'mvn package'
  }
  stage('Continuous Deployment')
  {
      sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.42.214:/var/lib/tomcat8/webapps/qaapp.war'
  }
  stage('Continuous Testing')
  {
      git 'https://github.com/selenium-saikrishna/FunctionalTesting.git'
      sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
  }
  stage('Continuous Deliver')
  {
      sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.82.148:/var/lib/tomcat8/webapps/prodapp.war'
  }
    
    
    
    
    
    
}
