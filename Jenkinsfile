pipeline{
	agent any
	parameters{
		//string(name:"DEPLOY_ENV",defaultValue:"development",description:"Select the target environment")
		string(name:"APP_VERSION",description:"Provide the version of the app")
	}
	environment{
		IMAGE_NAME="nirajvishwa894/restapi"
		PORT_MAPPING="8081:7000"	
	}
	stages{
		stage("building the application"){
			steps{
				sh """ echo "================building java application==============="
				mvn clean package
				echo "============building of application is completed==========="
				"""
			}
		}
		stage("Docker Image"){
   			steps{
          			sh """
           			echo "========Building the Docker Image ============"
           			docker build -t $IMAGE_NAME:'$APP_VERSION' .
           			echo "====== Building Image Completed ====="
         			"""      
   			} 
 		}		
	}//end of stages
}//end of pipeline
