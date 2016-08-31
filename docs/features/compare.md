## Autopilot vs Other Elasticsearch providers

Autopilot provisions Elasticsearch on your choice of infrastructure (AWS today), letting you tune software and settings without compromises of a multi-tenant environment.

There are several popular Elasticsearch providers: AWS, Bonsai, QBox, Elastic. In this post, we will highlight how Autopilot compares with AWS Elasticsearch, Bonsai and Elastic.co's cloud offering.


 

### Autopilot [v0.4]

- **Elasticsearch:** Supports v1.6, v1.7, v2.0, v2.1, v2.2 and v2.3 (latest). Intelligent default configurations, users can set and modify all the configurations.
- **Kibana (Visualization):** Suppported for all Elasticsearch versions.
- **Logging*:** Cluster logging supported via external apps like papertrail.
- **Plugins:** One-click install available for all the popular Elasticsearch and Kibana plugins.
- **Infrastructure:** Supports choosing cluster size, instance types, volume size, VPC and availability zones.
- **Security:** AWS security groups, Basic Authentication.
- **Data Backups:** Indefinite periodic hourly backups and cluster restore.
- **Pricing:** Fixed, $0.025 per instance hour (**$18 monthly** per instance).

### AWS Elasticsearch

- **Elasticsearch:** Supports Elasticsearch v1.5 and v2.3. Limited configuration support.
- **Kibana (Visualization):** Supported.
- **Logging:** Supported.
- **Plugins:** Not supported.
- **Infrastructure:** Supports choosing cluster size, instance types and volume size. VPC selection not supported.
- **Security:** AWS security groups and IAMs.
- **Data Backups:** Daily backups.
- **Pricing:** Varies by instance types, effective cost is comparable to Autopilot.


### Bonsai

- **Elasticsearch:** Supports ES v1.7 and v2.2. No configuration support.
- **Kibana (Visualization):** Not Supported.
- **Logging:** Supported.
- **Plugins:** Not supported.
-  **Infrastructure:** Multi-tenant by default, with support for dedicated clusters.
-  **Security:** Basic Authentication.
- **Data Backups:** Periodic hourly backups.
- **Pricing:** A 3-cluster dedicated plan costs **$600 monthly**, an equivalent Autopilot cluster would cost **3x less**.


### Elastic.co Cloud

-  **Elasticsearch:** Supports v1.7, v2.2 and v2.3. Sensible default configurations and ability to extend them.
-  **Kibana (Visualization):** Supported.
-  **Logging:** Supported.
-  **Plugins:** One-click install available for popular plugins.
-  **Infrastructure:** Multi-tenant setting, no choice.
-  **Security:** Supported with Shield (an Elasticsearch plugin).
- **Data Backups:** Periodic 30-min backups. 
-  **Pricing:** Starts at **$85 monthly** for production use, an equivalent Autopilot cluster would cost **4x less**.


---

### Summary

Autopilot offers the most configurable and affordable option for managing Elasticsearch deployments by far.

Update: 

* Starting ``v0.4``, Autopilot supports periodic backups with a point-in-time restore functionality.  
* Starting ``v0.3``, Autopilot creates SSL encrypted domains for the Elasticsearch cluster.
