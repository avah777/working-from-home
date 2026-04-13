pipeline{
    tools{
        jdk 'myjava'
        maven 'mymaven'
    }
	agent any
      stages{
           stage('Checkout with slave2'){
              steps{
		 echo 'cloning..'
                 git 'https://github.com/avah777/JUNECLASSPRO1.git'
              }
          }
          stage('Compile with slave1'){
              steps{
                  echo 'compiling..'
                  sh 'mvn compile'
	      }
          }
          stage('CodeReview with slave2'){
              steps{
		    
		  echo 'codeReview'
                  sh 'mvn pmd:pmd'
              }
          }
          
          stage('Package with master'){
              steps{
                  sh 'mvn package'
              }
          }
      }
}
