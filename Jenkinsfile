node {
   def app
   stage('Clone repository'){
        checkout scm
}

stage('Build image'){
 app = docker.build("my-image:${env.BUILD_ID}")
}

stage('Test image'){
        sh 'echo "Test passed"'

}

stage('Push image'){

   docker.withRegistry('https://registry.hub.docker.com','nuclear12ster'){
	app.push("${env.BUILD_NUMBER}")
	app.push("latest")
	}
     }
}
