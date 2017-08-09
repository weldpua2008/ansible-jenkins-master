# ansible-jenkins-master
Configure Jenkins Master from a scratch with Project-based Matrix Authorization Strategy


certification_repo - place to your Jenkins
Inside template folder - Jenkins jobs in format xml

Example playbook:
### Playbook
    ---
    - hosts: jenkins-master
      roles:
        - ansible-jenkins-master
      vars:
		my_jenkins_jobs:
		  - { name: "QA/Test", template: "QA/Test.xml" }
		  - { name: "QA/Test2", file: "QA/Test2.xml" }
		jenkins_cert_files:
		    - "/var/lib/jenkins/keys.pkcs12"
		    - "/var/lib/jenkins/jenkins.jks"
		jenkins_cloudbees_permissions:
		  - cloudbees_space:
		    com.cloudbees.plugins.credentials.CredentialsProvider.Create:
		      - weldpua2008@gmail.com      
		    com.cloudbees.plugins.credentials.CredentialsProvider.Delete:
		      - weldpua2008@gmail.com      
		    com.cloudbees.plugins.credentials.CredentialsProvider.ManageDomains:
		      - weldpua2008@gmail.com
		    com.cloudbees.plugins.credentials.CredentialsProvider.Update:
		      - weldpua2008@gmail.com
		    com.cloudbees.plugins.credentials.CredentialsProvider.View:
		      - weldpua2008@gmail.com
		    hudson.model.Computer.Build:
		      - weldpua2008@gmail.com
		    hudson.model.Computer.Configure:
		      - weldpua2008@gmail.com
		    hudson.model.Computer.Connect:
		      - weldpua2008@gmail.com
		    hudson.model.Computer.Create:
		      - weldpua2008@gmail.com
		    hudson.model.Computer.Delete:
		      - weldpua2008@gmail.com
		    hudson.model.Computer.Disconnect:
		      - weldpua2008@gmail.com
		    hudson.model.Computer.Provision:
		      - weldpua2008@gmail.com
		    hudson.model.Hudson.Administer:
		      - weldpua2008@gmail.com
		    hudson.model.Item.Build:
		      - weldpua2008@gmail.com
		    hudson.model.Item.Cancel:
		      - weldpua2008@gmail.com
		    hudson.model.Item.Configure:
		      - weldpua2008@gmail.com
		    hudson.model.Item.Create:
		      - weldpua2008@gmail.com
		    hudson.model.Item.Delete:
		      - weldpua2008@gmail.com
		    hudson.model.Item.Discover:
		      - weldpua2008@gmail.com
		    hudson.model.Item.Move:
		      - weldpua2008@gmail.com
		    hudson.model.Item.Read:
		      - weldpua2008@gmail.com
		    hudson.model.Item.Workspace:
		      - weldpua2008@gmail.com
		    hudson.model.Run.Delete:
		      - weldpua2008@gmail.com
		    hudson.model.Run.Replay:
		      - weldpua2008@gmail.com
		    hudson.model.Run.Update:
		      - weldpua2008@gmail.com
		    hudson.model.View.Configure:
		      - weldpua2008@gmail.com
		    hudson.model.View.Create:
		      - weldpua2008@gmail.com
		    hudson.model.View.Delete:
		      - weldpua2008@gmail.com
		    hudson.model.View.Read:
		      - weldpua2008@gmail.com
		    hudson.scm.SCM.Tag:
		      - weldpua2008@gmail.com
		    jenkins.metrics.api.Metrics.HealthCheck:
		      - weldpua2008@gmail.com
		    jenkins.metrics.api.Metrics.ThreadDump:
		      - weldpua2008@gmail.com
		    jenkins.metrics.api.Metrics.View:
		      - weldpua2008@gmail.com
		    org.jfrog.hudson.ArtifactoryPlugin.Promote:
		      - weldpua2008@gmail.com
		    org.jfrog.hudson.ArtifactoryPlugin.PushToBintray:
		      - weldpua2008@gmail.com
		    org.jfrog.hudson.ArtifactoryPlugin.Release:
		      - weldpua2008@gmail.com
		    hudson.model.Hudson.Read:
		      - weldpua2008@gmail.com

		my_jenkins_plugins:
			  build-pipeline-plugin:
			    enabled: yes  
			  ansible:
			    enabled: yes
			  artifactory:
			    enabled: yes
			  blueocean:
			    enabled: yes
			  slack:
			    enabled: yes
			  blueocean-dashboard:
			    enabled: yes
			  copy-to-slave:
			    enabled: yes
			  delivery-pipeline-plugin:
			    enabled: yes
			  envinject:
			    enabled: yes
			  google-login: 
			    enabled: yes
			  job-dsl:
			    enabled: yes
			  matrix-auth:  
			    enabled: yes
			  maven-plugin:
			    enabled: yes
			  pipeline-aggregator-view:
			    enabled: yes
			  pipeline-utility-steps:
			    enabled: yes
			  workflow-cps:
			    enabled: yes
			  build-user-vars-plugin:
			    enabled: yes
			  cloudbees-folder:
			    enabled: yes
			  role-strategy:
			    enabled: yes
			  repository-connector:
			    enabled: yes