pipeline {
	agent any
	
	stages {
		stage ("deploy to server") {
				
		steps {
		sshagent(['server-id']) {
    			sh 'rsync -rvu * ubuntu@ipaddress:~'
						}
		      }		

					   }

        stage ("Install Dependencies") {
            steps {
            
                sshagent(['server-id']) {
                    sh 'ssh ubuntu@ipaddress "cd ~ && composer install && php artisan storage:link && php artisan key:generate && php artisan optimize:clear"'
                			}
            	}
        
        				}
        
        	}	
        }
