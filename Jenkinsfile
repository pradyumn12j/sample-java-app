pipeline
{
    agent any
    stages
    {
        stage("Git checkout")
        {
            steps{git branch: 'master', url: 'https://github.com/pradyumn12j/sample-java-app'}
        }
        stage("code validate")
        {
            steps{withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
            sh'mvn validate'
}}
        }
        stage("code testing")
        {steps{withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
        
            sh'mvn install'
}}
        }
        stage("deploy to tomcat dev")
        {
        steps{sshagent (credentials: ['dev-deployments-v3']) {


            sh 'scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@172.31.21.23:/usr/share/tomcat/webapps'
  }}
        
        }
        
    }
}