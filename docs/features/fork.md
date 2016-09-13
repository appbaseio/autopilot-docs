## Database Forks

Database Forks work similar to Github's fork feature. Except for copying a code respoistory, an Autopilot fork operation creates a new database with the data snapshot of an existing database at a given point in time.

### Uses

Forks offer a safe way to:  
1. Run production data in development and staging environments for testing new mappings and query changes.  
2. Replicate a production data environment to a different infrastructure environment without risking downtime and data loss.   
3. Run performance and reliability benchmarks on exactly similar data states running on different infrastructure environments.

### How it works

##### STEP 0: Pick a DB cluster to fork from

A fork icon appears on the dashboard near the right portion of the cluster.  
![](https://i.imgur.com/QbMzIjs.png)  

as well as a static icon on right side of various cluster views.

![](https://i.imgur.com/lt8UNrv.png)  


##### STEP 1: Choose a cluster name for the (to be) forked DB and a point-in-time data snapshot

![](https://i.imgur.com/kuZ5IPb.png)


##### STEP 2: Configure Infrastructure 

The forked cluster can assume a completely different infrastructure environment: region of deployment, instances, disk volume, cluster size and yet guarantee an exact data state. 

##### STEP 3: Wait for the fork completion

A fork process transactionally provisions an infrastructure environment and starts with the DB state present in the selected snapshot. It can take up to 10 mins for the fork to complete sucessfully.

![](https://i.imgur.com/5eNeq7e.png)

Autopilot will show a notification alert on completion!
