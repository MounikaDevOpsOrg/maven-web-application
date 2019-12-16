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
}
