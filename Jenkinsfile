pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn -f javademos-master/ssgsems/pom.xml -B -DskipTests clean package'
        archiveArtifacts(fingerprint: true, artifacts: '**/target/*.war')
        sh '''mkdir /home/anagha/buildoutput/${BUILD_NUMBER}
cp **/target/*.war /home/anagha/buildoutput/${BUILD_NUMBER}'''
      }
    }

  }
}