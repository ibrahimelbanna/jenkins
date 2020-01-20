pipeline {

        agent {

        label 'master'

           }

	options {
	
	  buildDiscarder (logRotator(numToKeepStr:'2',artifactNumToKeepStr: '1'))

          }

        stages {

        stage('build'){

           steps {
                sh 'R CMD build .'

                 }

             }

         }
         stage('Unit Tests') {
            steps {
                // Invoke unit tests
              }
}
	post {

	    always {

		archiveArtifacts  artifacts: '*.tar.gz' , fingerprint: true

            }


        }   




  }