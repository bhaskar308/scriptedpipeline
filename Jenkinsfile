node {
    stage('continuousdownload') 
    {
    git 'https://github.com/MRaju2022/maven.git'
     }
     stage('continuousbuild') 
     {
    sh 'mvn package'
    }
    stage('continuousdeploy')
    {
    sh 'scp /home/ubuntu/.jenkins/workspace/sriptedproject/webapp/target/webapp.war ubuntu@172.31.20.99:/var/lib/tomcat9/webapps/testenv.war'
    }
    stage('continuoustesting') 
    {
    git 'https://github.com/MRaju2022/Testing.git'
    sh 'java -jar /home/ubuntu/.jenkins/workspace/sriptedproject/testing.jar'
}
stage('continuousdelivary')
{
   sh 'scp /home/ubuntu/.jenkins/workspace/sriptedproject/webapp/target/webapp.war ubuntu@172.31.20.113:/var/lib/tomcat9/webapps/prodenv.war' 
}
      } 
