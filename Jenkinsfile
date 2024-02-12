node{

def mavenHome = tool name: 'maven 3.9.6'

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])

echo "jenkins home dir is: ${env.JENKINS_HOME}"
echo "build number is: ${env.BUILD_NUMBER}"
echo "build id is: ${env.Build_ID}"
echo "job name is: ${env.JOB_NAME}"
echo "jenkins url is: ${env.JENKINS_URL}"
echo "build url is: ${env.BUILD_URL}"
echo "job url is: ${env.JOB_URL}"



stage('CheckOutCode'){
git branch: 'development', credentialsId: '5d74129e-d253-44ad-bd6c-a978c7cde0f8', url: 'https://github.com/msn-banking-projects-2023/maven-web-application.git'
}

stage('Build'){
sh"${mavenHome}/bin/mvn clean package"
}

  /*
stage('ExcuteSonarQubeReport'){
sh"${mavenHome}/bin/mvn clean sonar:sonar"
}

stage('UploadTheArtifactIntoTheNexus'){
sh"${mavenHome}/bin/mvn clean deploy"
}

stage('DeployAppIntoTomcat'){
sshagent(['e5ebf262-ee60-411a-8783-224c19320eb9']) {
 sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.37.161:/opt/apache-tomcat-9.0.83/webapps/"
}
}
*/
}
