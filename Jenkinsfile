 pipeline
      {
       agent any
       //spring application runs without maven tool as well
//         tools
//         {
//             maven 'MAVEN_HOME'
//         }

       stages {
          stage('Build') {
             steps {
                // Get some code from a GitHub repository
                git 'https://github.com/Pratiksha0401/AWS_Demo1.git'

                // Run Maven on a Unix agent.
                //sh "./mvnw -Dmaven.test.failure.ignore=true clean package"

                // To run Maven on a Windows agent, use
                //bat "mvn -Dmaven.test.failure.ignore=true clean install package"
                bat "mvn -Dmaven.test.failure.ignore=true clean package"
                }

                post {
                   // If Maven was able to run the tests, even if some of the test
                   // failed, record the test results and archive the jar file.
                   success {
                      junit '**/target/surefire-reports/TEST-*.xml'
                      archiveArtifacts 'target/*.jar'
                   }
                }
            }
       }
       
}
