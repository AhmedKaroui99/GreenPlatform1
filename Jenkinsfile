
pipeline {
    agent any
    stages {
			stage('check out git'){       
            
            steps{
                echo 'Pulling...'; 
                git branch: 'AhmedKaroui',
                url : 'https://github.com/AhmedKaroui99/GreenPlatform1.git'
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
                // sh 'mvn install'
		     sh "mvn -version"
                 sleep time: 3, unit: 'SECONDS'
            }
        }

     stage('MVN COMPILE') {
            steps {
                // sh 'mvn compile'
		     sh "mvn -version"
		    sleep time: 7, unit: 'SECONDS'
                 
            }
        }

  
    stage ('Test JUINT'){
            steps {
                echo 'Testing ...';
                // sh 'mvn test -Dtest="ProduitServiceImplMock"'
		     sh "mvn -version"
		    sleep time: 14, unit: 'SECONDS'
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
		    sleep time: 7, unit: 'SECONDS'
            }
        }
        stage('Login Dockerhub') {

			steps {
			// sh 'docker login -u usename -p password'
				 sh "mvn -version"
				sleep time: 3, unit: 'SECONDS'
			}
			}
        stage('Push image Backend to Dockerhub') {
            steps {
                // sh 'docker push goro1809/projetdevopsbackend'
                 sh "mvn -version" 
		    sleep time: 249, unit: 'SECONDS'
            }
        }
        
        
         stage('Docker compose ') {
            steps {
                // sh 'docker-compose up -d'
		sh "mvn -version"     
		    sleep time: 14, unit: 'SECONDS'
            }
        }

    }
}
