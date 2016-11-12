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

### Adam on SaltSide Journey
Adam talked about SaltStack journey, He discussed how slow their process was before few years and how they improved over the period of time. He lead us through the journey by sharing his learnings. Docker was his main discussion topic. The reason for chosing Docker was:
* To give engineers the freedom to choose best tool stack
* Infrastructure standardization.
* Dev and production parity

He then talked about his journey in SaltSide. He mentioned what they didn't have in 2014 and where they are right now.

* **On 2014:**
 * Mature container orchestration tool was not available.
 There were no official images for O.S.
 * Best practices were yet to be established
 
* **Kubernetes:**
Kubernetes helped SaltSide to boost their processes. This is how they are using it:
 * One cluster per region; multiple markets per cluster.
 * Decreased cost
 * Increase reliability
 * Move to maintained and active open-source project instead of end-of-life'd private internal tools
 * Increase velocity


 In their journey towards success, they faced multiple issues:
  * They can't cop up with everyday changing technology by their home grown tool Appolo. This becomes very slow and expensive in long run.
  * How to give client developers a functioning API platform to develop against?
  * How to give QA access to N number of service configurations?
  * How to give engineers a place to experiment outside production?
  * How to save everyone from configuring multiple services?
  
  These are the take aways from Adam's discussion:
   * Prefer Kubernetes/Mesos/DCOS instead rolling out your own solution
   * Prefer docker compose over manual docker commands
   * Google container Engine is the easiest way to get production ready container infrastructure.
   * Package up your distributed application instead of Engineer manage it themselves.
   * Include log and matrics system
   * Create development APIs instead of CLIs.
   * Distribute internal tools as docker image.
   * Prefer containerized workflow over host level dependencies.
   * Prefer one DockerFile per project
   * Prefer official docker images over internally maintained base images.
  
  
#### Lightening talks by various speakers

* Kitchen can be used as effective continuous integration tool for Chef cookbook development:
![alt](https://github.com/manish-devops/DevOps-Days-2016/blob/master/Diagrams/CI-for-Cookbooks/CI.jpg)


##### Devops in Networks:

Because of endless motivations like "maturity of server automation tools(chef, ansible, puppet), availability of routers for modelling, white box switches, opensource projects in Network space, container networking demanding simplicity" it is becomming very important for networking to have a devops culture. There can be multiple use cases for this.

* Configuration use cases
 * Network wide routing protocols
 * Configuring services like firewall and load-balancer
 * Declaring configuration rather than imperative
 
* Monitoring use cases:
 * Check cable mismatch
 * Inventory checking
 * Performance Monitoring
 * Check for error counters and thresholds
 * Analytics
 
 ![alt](https://github.com/manish-devops/DevOps-Days-2016/blob/master/Diagrams/DevOps-networking-Roadmap/DevopsNetworkingRoadmap.jpg)
 ![alt](https://github.com/manish-devops/DevOps-Days-2016/blob/master/Diagrams/DevOps-networking-Roadmap/DevopsNetworkingEcosystem.jpg)

