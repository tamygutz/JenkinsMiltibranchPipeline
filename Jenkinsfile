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
                    environment name: 'EXECUTE', value: 'TRUE'
            	steps {
                        echo script {
                            env.EXECUTE = 'True'
                        }
            	}
				 
				}
			} 

			stage('Third') {
				when {
                environment name: 'EXECUTE', value: 'FALSE'
            	}
				steps {
						echo 'Third stage can not be execute'
				}
			}
		}
}

    

