pipeline {

        agent {

        label 'master'

           }

	options {
	
	  buildDiscarder (logRotator(numToKeepStr:'2',artifactNumToKeepStr: '1'))

          }

        stages {

        stage ('build'){

           steps {
                sh 'R CMD build .'

                 }

             }

         }
		agent {

        label 'dev'

           }

	options {
	
	  buildDiscarder (logRotator(numToKeepStr:'2',artifactNumToKeepStr: '1'))

          }

        stages {

        stage ('build'){

           steps {
                sh 'R CMD build .'

                 }

             }

         }

	post {

	    always {

		archiveArtifacts  artifacts: '*.tar.gz' , fingerprint: true

            }


        }   




  }