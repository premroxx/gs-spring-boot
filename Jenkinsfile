node {
    def project = 'premkuma-bigbank-jenkins'
    def appName = 'java-springboot'
    def feSvcName = "springboot"
    def imageTag = "gcr.io/${project}/${appName}:${env.BRANCH_NAME}.${env.BUILD_NUMBER}"
    dir('${artifactId}'){
        stage('build'){
	        sh ("gcloud container builds submit -t ${imageTag} .")
    	}
/*     	stage('create docker image'){
		        sh 'docker login --username <user> --password <user>'
		        sh ("docker build -t address-rest-api .")
		        sh ("docker tag  address-rest-api <repo>/test:address-rest-api")
    	}
    	
    	stage('push docker image'){
			sh ("docker push prakashg84/test:${artifactId}")
    	}
    	
    	stage('create deployment'){
    	    sh 'kubectl delete deployments ${artifactId}api || true' 
	    sh 'kubectl create -f deployment.yaml --validate=false'
    	}
    	
    	stage('create service'){
	    sh 'kubectl delete services ${artifactId}apiservice || true'
	    sh 'kubectl create -f services.yaml --validate=false'
    	} */
    }
}
