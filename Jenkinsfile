pipeline {
    agent any
    stages {
        stage('Git Checkout'){
            
            steps{
                
                script{
                    
                    git branch: 'main', url: 'https://github.com/ara-dhanak/Ashok_JAVA.git'
                }
            }
        }
          stage(' Unit Test') {
            steps {
                sh ('mvn test');
            }
        }

          stage('Int testing') {
            steps {
                sh ('mvn verify -DskipUnitTests');
            }

        }
        	stage ('Code Quality') {
		    steps {
      			sh "mvn -Dmaven.test.failure.ignore sonar:sonar"
  			}
		}





       
	stage ('Code Quality') {
		steps {
      			sh "mvn -Dmaven.test.failure.ignore sonar:sonar"
  			}
		}
	    
        stage('Clean') {
            steps {
               sh "mvn -Dmaven.test.failure.ignore=true clean"
            }
        }
        
        stage('Validate') {
            steps {
                sh "mvn validate"
            }
        }
        
        stage('Compile') {
            steps {
                sh ('mvn compile');
            }
        }
        
        stage('Test') {
            steps {
                sh ('mvn test');
            }
        }
        
        stage('Package') {
            steps {
                sh ('mvn package');
            }
        }
        
        stage('Verify') {
            steps {
                sh ('mvn verify');
            }
        }
	 stage('Install') {
           steps {
                sh ('mvn install');
            }
        }
        
         
            
        stage('Stage-2 : Deployment - Deploy a Artifact devops-3.0.0-SNAPSHOT.war file to Tomcat Server') { 
            steps {
                sh 'curl -u admin:redhat@123 -T target/**.war "http://52.66.138.8:8080/manager/text/deploy?path=/aradhana&update=true"'
            }
        } 
  
          stage('Stage-3 : SmokeTest') { 
            steps {
                sh 'curl --retry-delay 10 --retry 5 "http://52.66.138.8:8080/aradhana"'
            }
        }
        
       
          
    }
}
