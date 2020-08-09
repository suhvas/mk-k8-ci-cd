
node{
  def Namespace = "pkapp"
  def ImageName = "suhvas/suhas-pridevops"
  def Creds	= "dockerhubaccount"
  def imageTag = "1.0"

  stage('Checkout'){
      git 'https://github.com/suhvas/jenkins-mvn-docker.git'
      //git 'https://github.com/maheshkharwadkar/mk-k8-ci-cd.git'
      //sh "git rev-parse --short HEAD > .git/commit-id"
      //imageTag= readFile('.git/commit-id').trim()



  }


    stage ('Push Docker image to DockerHub') {
		withCredentials([string(credentialsId: "${Creds}", variable: "${Creds}")]) {
		{
			sh "docker login -u suhvas -p ${dockerhubaccount}"
		}
		//sh 'docker push suhvas/suhas-pridevops:0.1.0'
		sh "docker build ${ImageName}:${imageTag}"
		//sh 'docker rmi suhvas/suhas-pridevops:0.1.0'
		//sh "docker rmi -t ${ImageName}:${imageTag}"
		}
	}

}

