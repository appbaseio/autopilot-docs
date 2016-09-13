## Elasticsearch Configurations

The latest stable Elasticsearch version is ``v2.4``. Autopilot always deploys with the latest stable minor Elasticsearch version as a default. There can however be good reasons for a version that's different from the latest version.

### Versions

There are two major versions that Elasticsearch users use today, ``1.x`` and ``2.x``. Many breaking changes were introduced in ``v2.0`` of Elasticsearch including major Query DSL changes, setting immutable mappings, introducing new aggregations. You can read about it [here](https://www.elastic.co/guide/en/elasticsearch/reference/current/breaking-changes-2.0.html).

#### 2.x

``v2.0``, ``v2.1``, ``v2.2``, ``v2.3``, ``v2.4`` - If you are using Elasticsearch for the first time, or don't require to interface with an existing 1.x version, we recommend picking one of these versions.

Of these, we recommend ``v2.4`` - it introduces the new [``/_reindex``](https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-reindex.html) endpoint, which comes in nifty as mappings are immutable and generally builds on the previous 2.x releases.

It also re-introduced field names with dots like ``foo.bar.z`` that were allowed by Elasticsearch up to ``v1.7`` but disabled starting ``v2.0`` due to mapping changes.

*Note:* If you are building an application that uses geo_point and maps based queries with percolators, we recommend using either ``v2.0`` or ``v2.1``. There is a [known issue](https://github.com/elastic/elasticsearch/issues/16832) on versions after 2.1.2 which will only be addressed starting ``v5.0``.

#### 1.x

``v1.6``, ``v1.7`` - Although these might sound ancient, v1.6 was released only a year ago on June 9, 2015. Contrast this to when v0.9 was released in July, 2010. Things have been moving fast in the Elasticsearch land. When we last checked, the official AWS Elasticsearch only supported v1.5.

Some benefits for picking ``v1.6`` and ``v1.7`` would be compatibility with your existing data cluster, Query DSL, or if you need mutable mappings.


### Cluster Configs

Elasticsearch allows specifying a configuration .yml file that is used while deploying a cluster. Autopilot comes with a good default configuration that can be extended by the user. A good reference point for available configurations can be [found here](https://www.elastic.co/guide/en/elasticsearch/reference/current/setup-configuration.html).

![](https://camo.githubusercontent.com/dedeabcbb5875557a3e825f1633807cf1bf8eb59/68747470733a2f2f692e696d6775722e636f6d2f325765535342442e706e67)

#### Common Configuration Options

#### HEAP SIZE
A good default here is 1/2 of your instance's RAM size.

#### MIN MASTER NODES
Min master nodes defines the minimum nodes needed for a stable cluster. To avoid split brain situations, where a cluster is split into two equal halves each able to form a cluster of their own - this parameter have a value > 50% and total nodes in the cluster should be an odd number.

#### INDEX # REPLICAS
Controls the cluster availability. An index with zero replicas will experience data loss when a single node becomes unavailable. **1** is a good default value here. For search heavy workloads, increasing this value will improve read performance of the cluster at the tradeoff of using more hardware.

#### INDEX # SHARDS
The number of primary shards used per index. A shard is the physical namespace in which data resides. An index is a logical namespace which routes to it's shards depending on the the setting here.

---

### Kibana

Kibana is a visualization framework for Elasticsearch data. One can define charts, dashboards and a variety of data viz scenarios through Kibana.

Autopilot supports provisioning Kibana along with the Elasticsearch cluster. It generates a **username:password** based auth token as a good default security for browsing Kibana.

Kibana also comes with it's own set of plugins. As of v0.1, Autopilot doesn't support installing Kibana plugins.

---

### Plugins

Elasticsearch has an up and coming plugin ecosystem to augment it's functionality. Two popular use-cases of plugins are cluster management and data visualization within Elasticsearch. Autopilot supports all the popular plugins for Elasticsearch.

![](https://camo.githubusercontent.com/add364f5f713bf445313637f104b2881e527d4df/68747470733a2f2f692e696d6775722e636f6d2f4f3443485952332e706e67)

If you would like Autopilot to support a particular plugin, send us a request at autopilot@appbase.io with subject "New plugin support request".
