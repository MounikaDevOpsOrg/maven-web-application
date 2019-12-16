node
{
  def mavenhome= tool name : "maven_3.6.3"
  
stage('to get the code from SCM')
{
git credentialsId: '6747513a-c106-4467-8921-f7968da6f004', url: 'https://github.com/MounikaDevOpsOrg/maven-web-application.git'
}
stage('to build')
  {
    sh "${mavenhome}/bin/mvn clean package"
  }
  stage('Sonar Report')
  {
    sh "${mavenhome}/bin/mvn clean package sonar:sonar"
  }
  stage("Upload Artifactories")
  {
    sh "${mavenhome}/bin/mvn clean package sonar:sonar deploy"
  }
  stage("to deploy the application into Tomcat")
  {
    sshagent(['e6e46bba-8930-4e88-870f-6e213c157ac6']) {
     sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.233.244.167:/opt/apache-tomcat-9.0.29/webapps/maven-web-application.war"
}
  }
  stage("Email Notification")
  {
    emailext body: '''Build is Over!

Thanks & Regards
Mounika Borra''', subject: 'Build is over', to: 'mounikaborra23@gmail.com,srinivasanramesh2014@gmail.com'
  }
}
