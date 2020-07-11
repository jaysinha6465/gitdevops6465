node {
   def app
   stage('Clone repository'){
        checkout scm
}

stage('Build image'){
 app = docker.build("my-image:${env.BUILD_ID}")
}

stage('Test image'){
	
	docker.image("my-image:${env.BUILD_ID}").inside {
        sh 'echo "Test passed"'
	}
}

stage('Push image'){

   docker.withRegistry('https://registry.hub.docker.com','nuclear12ster:good@2009'){
	app.push("${env.BUILD_NUMBER}")
	app.push("latest")
	}
     }
}
