node{
echo "Job Name is: ${env.JOB_NAME}"
echo "Node Name is: ${env.NODE_NAME}"

def mavenHome = tool name: 'maven3.9.1'

//Get the code from Github Repo
stage('CheckoutCode'){
git branch: 'development', credentialsId: 'f74ab2aa-c724-493b-8994-11f346cf7dc7', url: 'https://github.com/dhanudevopsengineer/maven-web-application.git'
}
//Do the build by using Maven Build tool
stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
}
/*
//Execute the SonarQube Report
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn sonar:sonar"
}
//Upload Artifacts into Artifactory Repo
stage('UploadArtifactsintoNexus'){
sh "${mavenHome}/bin/mvn deploy"
}
//Deply Application into TomcatServer
stage('DeployApplicationIntoTomcatServer'){
sshagent(['2b7b081c-83a5-4f2b-86e5-d60665c2ad5d']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@65.2.40.56:/opt/apache-tomcat-9.0.74/webapps"    
}
}
*/
}
