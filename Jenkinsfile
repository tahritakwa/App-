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
                    stage('build'){
	                steps{
	                 script{
	                  sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml "
	                   }
	                  }
	              }

                     stage('docker'){
                        steps{
                         script{
                          sh "ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml "
                           }
                          }
                      }
                      
                      stage('docker_register'){
                        steps{
                         script{
                          sh "ansible-playbook ansible/register.yml -i ansible/inventory/host.yml "
                           }
                          }
                        }

}
}

