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
				steps {
					if {
                	environment name: 'EXECUTE', value: 'FALSE'
					echo 'Third stage can not be execute'
            		}
				}
			}
		}
}

    

