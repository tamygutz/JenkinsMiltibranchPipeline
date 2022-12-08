pipeline {
	agent any
		stages {
			stage('First') {
				environment { 
                 		EXECUTE = 'TRUE' 
            		}
				steps {
						echo 'Updating Second Satge'
				}
			}

			stage('Second') {
				environment { 
                 		EXECUTE = 'TRUE' 
            		}
				when {
					environment name: 'EXECUTE', value: 'TRUE'
				}
				steps {
					echo 'Second stage can be executed'
				 
				}
			} 

			stage('Third') {
				environment { 
                 		EXECUTE = 'TRUE' 
            		}
				when {
                environment name: 'EXECUTE', value: 'FALSE'
            	}
				steps {
						echo 'Third stage can not be execute'
						script {
							env.EXECUTE="FALSE"
						}

				}
			}
		}
}

    

