 pipeline
      {
       agent any
        tools
        {
            maven 'M3'
        }

        stages
        {
          stage('Build App')
          {
            steps
             {
              git branch: 'openshift-aws', url: 'https://github.com/pavankjadda/BookStore.git'
              script {
                  def pom = readMavenPom file: 'pom.xml'
                  version = pom.version
              }
              sh "mvn install -DskipTests=true"
            }
          }
    }
}
