pipeline {
		agent any
				stages {
						stage('One') {
								steps {
										echo "stage 1"
								}
						}
						stage('Two') {
								steps {
										input('Do you want to proceed?')
								}
						}
						stage('Three') {
								when{
										not {
												branch "master"
										}
								}
								steps {
										echo "Hello"
								}
						}
stage('Four') {
				parallel {
					stage('Unit Test') {
										steps {
												echo "Running the unit tes..."
											}
					}
					stage('Integration test') 	{
											agent {
												docker {
														reuseNode false
														image 'ubuntu'
													}
												}
												steps {
													echo 'Running the integration test..'
												}
					}
				}
}
}
}