## DevOps Days India

I attended DevOps Days India conference on 4th and 5th Nov 2016. Details on devops days India can be found [here](http://devopsdaysindia.org/index.html#header). The event was filled with discussions around multiple devops aspects. Kubernetes was the hottest topic among all. Speakers talked about ChatOps, security issues in current containerised infrastructure, Docker, OpenShift, Rancher, Terraform, Chef, Hadoop Clusters, Monitoring and Alerting solutions. Speakers like IAN LEWIS(Developer Advocate for Google Cloud Platform), AJEY GORE(CTO for Go-Jek), AKASH MAHAJAN(director for Appsecco) and many more shared their knowledge and learnings in this conference. Let's have a quick look on these discussions:

### Ian on Kubernetes:
Kubernetes is a platform to build distributed systems. This is how it works:
 * User creates deployment
 * API server saves info to etcd
 * CM finds Deployment and creates ReplicaSet, which creates pods (Unscheduled)
 * SScheduler schedules pods
 * Kublet sees pod scheduled to it and tells docker to run the container.
 * Docker pulls and runs the container.
