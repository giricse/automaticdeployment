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
	 git 'https://github.com/giricse/automaticdeployment.git'
      }
    }
    stage('mvn install'){
      steps{
	echo ' maven clean & install'
	sh 'mvn clean'
	sh 'mvn install'
      }
    }
    stage('ansible syntax check'){
      steps{
       echo 'to check ansible syntax check'
       sh 'ansible-playbook javainstall.yml --syntax-check'
       sh 'ansible-playbook tomcatinstall.yml --syntax-check'
      }
    }
    stage('ansible playbook execution'){
	    steps{
		    echo 'Executing playbooks'
		    sh 'ansible-playbook javainstall.yml'
		    sh 'ansible-playbook tomcatinstall.yml'
}
  }
}
