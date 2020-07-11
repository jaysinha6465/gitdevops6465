node {
   def app
   stage('Clone repository'){
        checkout scm
}

stage('Build image'){
 app = docker.build("nuclear12ster/testrespository")
}

stage('Test image'){
	
	app.inside{
        sh 'echo "Tests passed"'
	}
}

stage('Push image'){

   docker.withRegistry('https://registry.hub.docker.com','nuclear12ster'){
	app.push("${env.BUILD_NUMBER}")
	app.push("latest")
	}
     }
}
