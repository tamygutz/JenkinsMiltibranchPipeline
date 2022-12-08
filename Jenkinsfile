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
				steps {
					when {
                    environment name: 'EXECUTE', value: 'TRUE'
				    echo 'Second stage can be executed'
            	}
				 
				}
			} 

			stage('Third') {
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

    

