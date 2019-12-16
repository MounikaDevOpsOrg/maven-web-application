node
{
  echo "GitHub BranhName ${env.BRANCH_NAME}"

  echo "Jenkins Job Number ${env.BUILD_NUMBER}"

  echo "Jenkins Node Name ${env.NODE_NAME}"

 
  echo "Jenkins Home ${env.JENKINS_HOME}"

  echo "Jenkins URL ${env.JENKINS_URL}"

  echo "JOB Name ${env.JOB_NAME}"

  properties([

    buildDiscarder(logRotator(numToKeepStr: '6')),

    pipelineTriggers([

        pollSCM('* * * * *')

    ])

  ])
  def mavenhome= tool name : "maven_3.6.3"
  
stage('to get the code from SCM')
{
git credentialsId: '6747513a-c106-4467-8921-f7968da6f004', url: 'https://github.com/MounikaDevOpsOrg/maven-web-application.git'
}
}
