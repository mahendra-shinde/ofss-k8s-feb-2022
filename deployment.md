# Deployment Object

- Manages deployment and updates to application.
- Manages Replica-Set.
- Maintain the deployment history, undo previous updates or deploy newer version.


## Why deployment ? 

- Deployment Frequency affects "Downtime" / "Uptime"
- Higher Deployment frequency will result in "Higher" downtime !

Green/Blue deployment pattern ?

  Two "Envs" for application 
		PROD Env			10.0.2.17
	   STAGING Env	10.0.2.25

	Deploy to STAGING env, run tests & performance
		Switch PROD & STAGING /// switch actually takes less time !

--------------------------------
Kubernetes has "Rolling Update" strategy
	On every "Update" / "deployment", kubernetes would:
		1. Create NEW replicaSet for Newer version (initialially set to ZERO)
		2. Scale DOWN the Older version & Scale UP New version.
		3. Older ReplicaSet would be set to ZERO count.

	Kubernetes has "UNDO" feature
		1. Scale OLDER replicaset UP
		2. Scale NEWER replicaset DOWN

Limitation of Rolling Updates:
-------------
Higher compute resources while rolling updates
	App1 need "3" replicas, each replica need 1 cpu & 2 Gb RAM
		App1 ==> 3 Cpus and 6 GB RAM
	After "rollingUpdate", you MUST ensure that, you have 6 CPUs and 12 GB RAM

Recreate Strategy:
--------
Kubernetes will scale down OLD replicaset to ZERO, and start creating NEW replicaset
only after OLD replicaset count reached zero.

If an App can "tolerate" downtime of few minutes, then Choose "recreate strategy"
If an App cannot "tolerate" a downtime of few minutes, then choose "Rolling Update"