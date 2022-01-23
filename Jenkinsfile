 pipeline
      {
       agent any
        tools
        {
            maven 'MAVEN_HOME'
        }

        stages
        {
          stage('Build App')
          {
            steps
             {
              git branch: 'master', url: 'https://github.com/Pratiksha0401/AWS_Demo1.git'
              script {
                  def pom = readMavenPom file: 'pom.xml'
                  version = pom.version
              }
              sh "mvn clean -DskipTests=true"
            }
          }
    }
}
