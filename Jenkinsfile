pipeline {
	agent any
		stages {
			stage('First') {
				environment { 
                 		EXECUTE = 'TRUE' 
            		}
				steps {
                        script {
                                             
                                env.EXECUTE="True"                     

                        }
                }
			}

			stage('Second') {
                when {
                    environment name: 'EXECUTE', value: 'TRUE'
				}
				steps {
                         echo script {
                            echo $EXECUTE
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

    

