node{
def mavenHome = tool name: "maven3.8.4"

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'RebuildSettings', autoRebuild: false, rebuildDisabled: false], [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * *  *  *')])])

stage('CheckoutCode'){

git branch: 'development', credentialsId: '69c370d6-30e9-4ad2-b97d-2b3a76398aeb', url: 'https://github.com/MithunTechnologiesDevOps/maven-web-application.git'
}

stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
}

/*
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn sonar:sonar"
}

stage('UploadArtifactsIntoNexus'){
sh "${mavenHome}/bin/mvn deploy"
}

stage('DeployAppintoTomcatServer'){

sshagent(['4f0deabf-417d-42cb-b0e4-62e8bbae226c']) {
   sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war  ec2-user@54.252.215.90:/opt/apache-tomcat-9.0.54/webapps/"
}
}

stage('SendEmailNotification'){

emailext body: '''Build Over..

Regards,
Mithun Technologies,
9980923226''', subject: 'Build Over', to: 'devoptrainingblr@gmail.com'
}
*/

}
