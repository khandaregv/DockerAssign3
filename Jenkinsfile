pipeline {
		agent {
			label {
				label "built-in"
				customWorkspace "/mnt/master"
			}	
		}
				stages {
					stage ("One"){
						steps {
							sh "sudo docker ps -aq | xargs -r sudo docker rm -f"
							sh "sudo docker volume prune -f"
							sh "sudo chmod -R 777 /mnt/master"
							sh "sudo docker volume create V3"
							sh "sudo docker run -itdp 8080:80 -v /mnt/master:/usr/local/apache2/htdocs/ --name Cont3 httpd bash"
						}		
					}
				}		
}
