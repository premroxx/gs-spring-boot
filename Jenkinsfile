node {
    	def mvnHome
    	
    	stage('checkout'){
        
        mvnHome = tool 'M3'
        git url: 'https://github.com/premroxx/gs-spring-boot.git'
    
        sh "git rev-parse HEAD > .git/commit-id"
        def commit_id = readFile('.git/commit-id').trim()
        println commit_id
        }
    
    dir('${artifactId}'){
        stage('build'){
	        sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean install"
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
