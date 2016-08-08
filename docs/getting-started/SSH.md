# Configuring SSH Access

One of the prime advantages of using Autopilot system is the ability to have control over the Elasticsearch cluster. Autopilot provides complete access to the underlying machine via SSH.

### Step 1: Go to SSH Access Tab

![](https://i.imgur.com/PRRz6Qg.png)

Once you have deployed a cluster, you should be able to go to the ``SSH ACCESS`` tab. Add a new SSH Key.

### Step 2: Add a public SSH Key

You can configure one or more public SSK Keys with the Autopilot UI.

![](https://i.imgur.com/XebFPkd.png)

Once successfully added, the dashboard should show the key fingerprint.

![](https://i.imgur.com/s6KZ28P.png)

### Step 3: SSH'ing

``ssh -i /path/to/private.key core@cluster_instance_ip``

**Note:** The machine username is ``core``, because all Autopilot deployed clusters use CoreOS as the operating system. 

![](https://i.imgur.com/n4MiK5Q.png)

Voila! You now have full access to the machines in the cluster.
