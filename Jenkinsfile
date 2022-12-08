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
				when {
					env.EXECUTE = 'True'
				}
				steps {
					echo script {
						env.EXECUTE = 'True'
					}
				 
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

    

