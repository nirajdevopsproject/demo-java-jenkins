pipeline{
	agent any
	stages{
		stage("building the application"){
			step{
				sh """ echo "================building java application==============="
				mvn clean package
				echo "============building of application is completed==========="
				"""
			}
		}
	}//end of stages
}//end of pipeline
