## DevOps Days India

I attended DevOps Days India conference on 4th and 5th Nov 2016. Details on devops days India can be found [here](http://devopsdaysindia.org/index.html#header). The event was filled with discussions around multiple devops aspects. Kubernetes was the hottest topic among all. Speakers talked about ChatOps, security issues in current containerised infrastructure, Docker, OpenShift, Rancher, Terraform, Chef, Hadoop Clusters, Monitoring and Alerting solutions. Speakers like IAN LEWIS(Developer Advocate for Google Cloud Platform), AJEY GORE(CTO for Go-Jek), AKASH MAHAJAN(director for Appsecco) and many more shared their knowledge and learnings in this conference. Let's have a quick look on these discussions:

### Ian on Kubernetes:
Ian started his discussion by showing the evolution of Kubernetes:
![alt The Clusters of Old](https://github.com/manish-devops/DevOps-Days-2016/blob/master/Diagrams/IAN/The%20Clusters%20of%20Old.jpg)
![alt Container Cluster](https://github.com/manish-devops/DevOps-Days-2016/blob/master/Diagrams/IAN/Container%20Clusters.jpg)
![alt 10000 Foot View Of Kubernetes Evolution](https://github.com/manish-devops/DevOps-Days-2016/blob/master/Diagrams/IAN/10000FootViewOfKubernetesEvolution.jpg)


Kubernetes is a platform to build distributed systems. This is how it works:
 * User creates deployment
 * API server saves info to etcd
 * CM finds Deployment and creates ReplicaSet, which creates pods (Unscheduled)
 * SScheduler schedules pods
 * Kublet sees pod scheduled to it and tells docker to run the container.
 * Docker pulls and runs the container.
 
 
### Rajat on ChatOps:
Architecture diagram for ChetOps is as follows:
![alt ChatOps-Architecture](https://github.com/manish-devops/DevOps-Days-2016/blob/master/Diagrams/RajatOnChatOps/Architecture-ChatOps.jpg)
 
ChatOps Features:
 * On demand infra provision
 * APIs monitoring
 * Deployments to Cloud / Local Data Center
 * Alert Notification over Email and Chat
 * Instance Details
 
 
### Madhu Akula on Infrastructure Security Monitoring:
Madhu discussed about the need to monitoring and how we can make our infrastructure more secure by following simple approaches. Madhu uses Logstash, ElasticSearch and Kibana as full stack monitoring tools. [Tick Stack](https://www.influxdata.com/time-series-platform/) and [GrayLog](https://www.graylog.org/) can be used as full stack ulternatives for monitoring. 

Guidelines for Security shared by Madhu:
* Harden the base server with traditional security techniques.
* Use SSH key for login.
* Remove root login.
* Use randomly generated passwords
  * openssl rand -base64 24
* Enable the host firewall and allow only connections from specific IPs
* Use SSL certificates and enable HTTPS for ElasticSearch, Lagstash and Kibana (Eg. Lets encrypt)
* Use search guard for granular permissions and role based authentication for ELK(Shield is an alternative)


 
