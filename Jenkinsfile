node{

def mavenHome = tool name: "maven3.8.4"

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])

stage('checkoutCode')
{
git branch: 'development', url: 'https://github.com/harsha14ars/maven-web-application.git'
}

stage('Build')
{
sh "${mavenHome}/bin/mvn clean package"
}
/*
stage('ExecuteSonarqubeReport')
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}

stage('UploadArtifactsIntoNexus')
{
sh "${mavenHome}/bin/mvn deploy"
}

stage('DeployAppIntoTomcatserver')
{
sshagent(['8f68ef25-cb22-485c-8c38-f100a5bb1385']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.109.5.85:/opt/apache-tomcat-9.0.63/webapps"

}

}
*/
}
