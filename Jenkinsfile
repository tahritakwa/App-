pipeline
	{
	          agent any
	           stages {
	             stage('Pull') {
	              steps{
	               script{
	                 checkout([$class: 'GitSCM', branches: [[name: '*/master']],
	                  userRemoteConfigs: [[
	                           credentialsId:'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',
	                     url:'https://github.com/tahritakwa/App-.git']]])
	          }
	       }
	      }
                    stage('Install'){
	                steps{
	                 script{
	                  sh "sudo npm install "
	                   }
	                  }
	              }
                    stage('docker'){
	                steps{
	                 script{
	                  sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml "
	                   }
	                  }
	              }
}
}

