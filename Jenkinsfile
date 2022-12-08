pipeline {
	agent any
		stages {
			stage('First') {
				environment { 
                 		EXECUTE = TRUE 
            		}
				steps {
						echo "Updating Second Satge"
				}
			}

			stage('Second') {
				when {
                environment name: 'EXECUTE', value: 'TRUE'
            	}
				steps {
						echo 'Second stage can be executed' 
				}
			} 

			stage('Third') {
				when {
                environment name: 'EXECUTE', value: 'FALSE'
            	}
				steps {
						echo "Third stage can't be execute"
				}
			}
		}
}

    

