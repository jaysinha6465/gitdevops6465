node {
   def app
   stage('Clone repository'){
        checkout scm
}

stage('Build image'){
 app = docker.build("test_image","./jaysinha6465/gitdevops6465")
}

stage('Test image'){
  app.inside{
      sh 'echo "Test passed"'
}
}

stage('Push image'){

   docker.withRegistry('https://registry.hub.docker.com','nuclear12ster'){
	app.push("${env.BUILD_NUMBER}")
	app.push("latest")
	}
     }
}