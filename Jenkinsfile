  stages {
        
        stage('ard'){
            
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
            stage('Int testing'){
            
            steps{
                
                script{
                    
                    sh 'mvn verify -DskiUnitTests'
                }
            }
        }

  }
  