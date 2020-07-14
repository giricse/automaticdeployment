pipeline {
  agent any
  tools {
    jdk 'jdk1.8'
    maven 'maven3'
  }
  stages{
    stage('git pull'){
      steps{
         echo 'this stage is for pull repo'
	 git 'https://gitlab.com/jagarlamudirajesh34/ansible1.git'
      }
    }
    stage('mvn install'){
      steps{
	echo ' maven clean & install'
	sh 'mvn clean'
	sh 'mvn install'
      }
    }

  }
}
