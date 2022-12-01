pipeline {
	agent none
	stages {
		stage (‘NonParallel’) {
			agent {
				label 'Master'
			}
			steps {
				echo 'This stage will be executed first';
			}
		}
		stage (‘RunTests’) {
		    parallel {
			    stage (‘TestOnWindows’) {
				    agent {
					    label 'Windows_Slavenode1'
				    }
				    steps {
					    echo 'Task1 on Agent';
			    	}
			    }
			   stage (‘Test_On_Master’) {
				    agent {
					    label 'Master'
				    }
				    steps {
					    echo 'Task1 on Master';
				    }
			    }

		    }

	    }
	}
	
}
