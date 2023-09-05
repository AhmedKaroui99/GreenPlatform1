pipeline {
    agent any
    stages {
			stage('check out git'){       
            
               steps {
                script {
                    // Define the credentials ID
                    def credentialsId = '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'

                    // Use the withCredentials step to securely pass the credentials
                    withCredentials([string(credentialsId: credentialsId, variable: 'GIT_TOKEN')]) {
                        sh '''
                            echo 'Pulling...'
                            git config --global credential.helper "store --file=/tmp/git-credentials"
                            echo "https://${GIT_TOKEN}@github.com/AhmedKaroui99/GreenPlatform1.git" > /tmp/git-credentials
                            git clone https://${GIT_TOKEN}@github.com/AhmedKaroui99/GreenPlatform1.git
                        '''
                    }
                }
            }
        }
       stage('Testing maven') {
            steps {
                sh "mvn -version"
            }
        }

	stage('MVN CLEAN') {
            steps {
                sh 'mvn clean'
                 
            }
        }

    stage('MVN INSTALL') {
            steps {
                sh 'mvn install'
                 
            }
        }

     stage('MVN COMPILE') {
            steps {
                sh 'mvn compile'
                 
            }
        }

  
    stage ('Test JUINT'){
            steps {
                echo 'Testing ...';
                sh 'mvn test -Dtest="ProduitServiceImplMock"'
            }
        }
                

		// stage('MVN SONARQUBE') {
  //           steps {
  //               sh 'mvn sonar:sonar -Dsonar.login=admin -Dsonar.password=sonar'
  //           }
  //       }
        
       
       stage('Build Docker image Backend') {
            steps {
                // sh 'docker build -t goro1809/projetdevopsbackend . '
		sh "mvn -version"                  
            }
        }
        stage('Login Dockerhub') {

			steps {
			sh 'docker login -u goro1809 -p Ahmed1999Amin2004'
			}
			}
        stage('Push image Backend to Dockerhub') {
            steps {
                // sh 'docker push goro1809/projetdevopsbackend'
                 sh "mvn -version" 
            }
        }
        
        
         stage('Docker compose ') {
            steps {
                // sh 'docker-compose up -d'
		sh "mvn -version"                 
            }
        }

    }
}
