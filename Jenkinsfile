pipeline
{
    agent any
    stages
    {
        stage("Git checkout")
        {
            steps{git branch: 'master', url: 'https://github.com/pradyumn12j/sample-java-app'}
        }
<<<<<<< HEAD
        stage('execute unit test framework')
{steps {withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) 
{
    sh 'mvn test'   // valitade , compile then run test
}} }

stage('generate artifact and store in local maven repository')
{steps {withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) 
{
    sh 'mvn clean install -DskipTests'    //skip test, it also generates artifact, clean the workspace folder
}} }
stage("deploy to tomcat dev")
=======
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
>>>>>>> 051096d4f2d9bfbd5ad523ce827ed78d00c715f7
        {
        steps{sshagent (credentials: ['dev-deployments-v3']) {


<<<<<<< HEAD
            sh 'scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@172.31.19.127:/usr/share/tomcat/webapps'
  }}
        
        }

    }
}