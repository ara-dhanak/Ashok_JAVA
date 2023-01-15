  stages {
        
        stage('Git Checkout'){
            
            steps{
                
                script{
                    
                    git branch: 'main', url: 'https://github.com/ara-dhanak/Ashok_JAVA.git'
                }
            }
        }
        stage('UNIT testing'){
            
            steps{
                
                script{
                    
                    sh 'mvn test'
                }
            }
        }
            stage('Int testing'){
            
            steps{
                
                script{
                    
                    sh 'mvn verify -DskiUnitTests'
                }
            }
            }
             stage('Build') {
            steps {
               sh "mvn  clean"
            }
        }
         stage('Validate') {
            steps {
                sh "mvn validate"
            }
        }

         stage('Maven Compile ') {
            steps {
                sh "mvn compile"
            }
        }
        stage ('Code Quality') {
		steps {
      			sh "mvn -Dmaven.test.failure.ignore sonar:sonar"
  			}
		}



        
        }


  