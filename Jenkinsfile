pipeline {
    agent any
    tools{
        maven "MAVEN_HOME"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Hello World'
            }
        }

        stage('Dev') {
             steps {
                 echo 'Hello World'
                 }
             }

        stage('Deploy') {
             steps {
                  echo 'Hello World'
             }
        }

        stage('Build App'){

//              steps{
//                  git branch: 'openshift-aws', url: 'https://github.com/pavankjadda/BookStore.git'
//                       script {
//                           def pom = readMavenPom file: 'pom.xml'
//                           version = pom.version
//                       }
//                       sh "mvn install -DskipTests=true"
//                     }
//                   }
            steps {

                     echo 'Building App'
                  // Get some code from a GitHub repository
                  git 'https://github.com/Pratiksha0401/AWS_Demo1.git'

                  // Run Maven on a Unix agent.
                  //sh "mvn -Dmaven.test.failure.ignore=true clean package"

                  // To run Maven on a Windows agent, use
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
