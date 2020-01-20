pipeline {

        agent {

        label 'master'

           }

	options {
	
	  buildDiscarder (logRotator(numToKeepStr:'2',artifactNumToKeepStr: '1'))

          }

        stages {

        stage('Unit Tests'){
            steps {
                echo 'hello world'
              }
         }
        stage('build'){

           steps {
                sh 'R CMD build .'

                 }

             }
        }
         
	post {

	    always {

		archiveArtifacts  artifacts: 'GIT_COMMIT.tar.gz' , fingerprint: true

            }


        }   




  }