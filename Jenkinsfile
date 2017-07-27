#!groovy
node {
    def gradleHome = tool 'gradle-2.13'
	stage 'Sending out Approval Request'
	mail (to: 'jugal.porwal@capsilon.com',
         subject: "Job '${env.JOB_NAME}' (${env.BUILD_NUMBER}) is waiting for input",
         body: "Please go to ${env.BUILD_URL}.");
	input message: 'Approve packaging?', submitterParameter: 'isApproved'
	if (isApproved == true){
		echo "Packaging was approved"
	}
}