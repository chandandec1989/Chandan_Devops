# Kubernetes:-
	kubectl get pods 
	kubectl get pods -n dev
	kubectl describe pods <pod_name> -n dev
	kubectl rollout restart deployment <deployment-name>
	kubectl get svc -n dev
	kubectl get ingress -n dev
	
	
# Kubernetes Troubleshoot:-
	-> logs + Events + Describe + check resources + Networks = RootCause

1. Pod is not running/Pending:-
	a. check pod status     :- kubectl get pods -A
	b. Get pods info detail :- kubectl describe pod <pod-name> -n <namespace>
	c. check events         :- kubectl get events --sort-by=.metadata.creationTimestamp
	d. quick pod status quickly:-
		1. kubectl get pods -o wide
		2. kubectl describe pod <pod-name>
		3. kubectl logs <pod-name> -n <namespace>
		4. kubectl get events
		
	e. Common reasons:-
		1. Image not found / wrong image name
		2. Insufficent resources (cpu/memory)
		3. PVC not bound
		4. NodeSelector / Taints / Tolerations
		5. Failed Scheduling
		
		
2. Pod is Crashing / Restarting (CrashLoopBackoff):-
	a. check logs                     :- kubectl logs <pod-name> -n <namespace>
	b. check previous container logs  :- kubectl logs <pods> -n <namespace> --previous
	c. Check exit code                :- kubectl get pod <pod> -o jsonpath = '{.status.containerStatuses[o].state}'
	d. Common reasions:-
		i. Application Error
		ii. OOMKILLED (Out of Memory)
		iii. Wrong Configuration / ENV Variables
		iv. Liveness / Readness Probe failures
	e. IF OOMKILLED:-
			i. Kubectl describe pod <podname>
			ii. Check the last state / reason
			iii.Check node memory :- kubectl top node

			
3. Pod is not able to reach other services / Network issues.
	a. Test Connectivity from pod:-
		i. kubectl exec -it <pod> -- sh
		# inside pod, run: curl <service-name> or ping <ip>
	b. check service & endpoints:-
		i. kubectl get svc
		ii. kubectl get endpoints
	c. check network policies / firewell / security group (cloud)
	

4. Service is not working:-
	a. check service details:- kubectl describe svc <svc>
	b. check endpoints:- kubectl get endpoints <svc>
	c. verify selector matches pod labels
	d. check if pods are healthy and running
	
5. Node related issues:-
	a. check node status :- kubectl get nodes
	b. check node conditions : kubectl describe node <node-name>
	c. check kubelet logs : journalctl -u kubelet
	d. check if node is NotReady (network, disk, etc)

6. PVC / Storage issues:-
	a. check PVC status : kubectl get pvc
	b. check PV : kubectl get pv
	c. check storage class : kubectl get sc
	d. Events : kubectl get events | grep -i pvc
	
7. Logs & Debugging tips:-
	a. Use --since to get recent logs : kubectl logs <pod> --since=10m
	b. Follow logs : kubectl logs -f <pod>
	c. check all container in a pod : kubectl logs <pod> -c <container>
	d. For multi-container pods : kubectl logs <pod> -c <container>
	e. Describe everything(pods, svc, deploy, etc) : kubectl describe <resource>
	f. check cluster events : kubectl get events --all -namespace
	
8. Useful Commands:-
	a. kubectl get pods -A
	b. kubectl describe pod <pod>
	c. kubectl logs <pod>
	d. kubectl get svc
	e. kubectl get nodes 
	f. kubectl top pod 
	g. kubectl top node 
	h. kubectl get events
	i. kubectl rollout status deploy/<name>
	j. kubectl get all -n <ns>
	
# Quick Checklist:-
	a. Pod status & Events
	b. logs (Currents + Previous)
	c. check resources (CPU/Memory)
	d. Service, endpoints, network
	e. Node Status
	f. PVC / Storage
	g. K8s events & describe
	
# Remember:-
	a. Start with kubectl get pods -A
	b. use describe to understand the issues
	c. logs tell you what happened
	d. Event tell you why
	e. check resources (cpu/memory/disk)
	f. Think layer by layer (pod -> service -> Node -> Network -> Storage)
	
	
