pipeline
{
    agent any 
    stages
    {   
        stage ('building the code using maven')
        {
            steps
            {
               withMaven (maven:'MAVEN_HOME')
                {
                    sh 'mvn install'
                }
            }
        }
        stage ('deploy to tomcat') {
            steps {
                sh 'cp -R /var/lib/jenkins/workspace/declarative/target/* /var/lib/jenkins/apache-tomcat-11.0.18/webapps/'
            }
        }
    }
}
