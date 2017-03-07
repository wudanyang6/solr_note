<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#orgb62a448">1. Issues</a>
<ul>
<li><a href="#orge5bfc74">1.1. 学习时遇到的问题</a>
<ul>
<li><a href="#orgb905977">1.1.1. Q: ZooKeeper JMX enabled by default Using config: <i>Users/wudanyang/self/zoo/bin</i>../conf/zoo.cfg Error contacting service. It is probably not running.</a></li>
<li><a href="#orgac105e8">1.1.2. Q: ZooKeeper 执行 bin/zkServer.sh status 说未启动</a></li>
<li><a href="#org4b9cef1">1.1.3. Q: SolrCore Initialization Failures</a></li>
<li><a href="#org203ed60">1.1.4. Q: 通过api创建collection时, 返回localhost未返回任何数据</a></li>
<li><a href="#org10f7415">1.1.5. Q: Cannot create collection tinycollection. Value of maxShardsPerNode is 1, and the number of live nodes is 4. This allows a maximum of 4 to be created. Value of numShards is 2 and value of replicationFactor is 3. This requires 6 shards to be created (higher than the allowed number)&lt;/str&gt;</a></li>
<li><a href="#org6835cff">1.1.6. Q: 在zookeeper中找不到配置文件</a></li>
<li><a href="#orge732ca6">1.1.7. Q: 为何在6.*以上的solr中store=false 仍然能看到字段被返回了</a></li>
<li><a href="#org724536b">1.1.8. Q: int类型为何docValues=false与stored=false还能在结果中看到字段</a></li>
<li><a href="#org129c4de">1.1.9. Q: 从 example/example-DIH/solr/ 中复制solr.xml 作为cloud的配置文件无法生效</a></li>
<li><a href="#org93c7b8a">1.1.10. Q: 为什么找不到 Can't find resource 'schema.xml'</a></li>
</ul>
</li>
</ul>
</li>
</ul>
</div>
</div>

<a id="orgb62a448"></a>

# Issues


<a id="orge5bfc74"></a>

## 学习时遇到的问题


<a id="orgb905977"></a>

### Q: ZooKeeper JMX enabled by default Using config: *Users/wudanyang/self/zoo/bin*../conf/zoo.cfg Error contacting service. It is probably not running.

A: bin/zkServer.sh start-foreground 可以查看到


<a id="orgac105e8"></a>

### Q: ZooKeeper 执行 bin/zkServer.sh status 说未启动

A: ps aux | grep zookeeper
查看是否存在


<a id="org4b9cef1"></a>

### Q: SolrCore Initialization Failures

A: 未上传配置
sh zkcli.sh -cmd upconfig -zkhost localhost:2181 -confname gettingstarted -confdir ../../../server/solr/configsets/basic<sub>configs</sub>/conf


<a id="org203ed60"></a>

### Q: 通过api创建collection时, 返回localhost未返回任何数据

A: 请求地址应该是solr服务器，而不是zookeeper服务器。
localhost:8983/solr/admin/collectinos?action=CREATE&name=yang&numShards=1&replicationFactor=3&collection.configName=yang


<a id="org10f7415"></a>

### Q: Cannot create collection tinycollection. Value of maxShardsPerNode is 1, and the number of live nodes is 4. This allows a maximum of 4 to be created. Value of numShards is 2 and value of replicationFactor is 3. This requires 6 shards to be created (higher than the allowed number)</str>

A:将replicationFactor降低
<http://localhost:8983/solr/admin/collections?action=CREATE&name=yang&collection.configName=yang&numShards=1&replicationFactor=1&wt=json>


<a id="org6835cff"></a>

### Q: 在zookeeper中找不到配置文件

A: 配置文件疑似在上传到zookeeper时放到了名为zoo<sub>data</sub>/version-{num}/log.number的二进制文件中


<a id="orge732ca6"></a>

### Q: 为何在6.\*以上的solr中store=false 仍然能看到字段被返回了

A: 在6.\*之后，string 的 docValues=true 为默认值


<a id="org724536b"></a>

### Q: int类型为何docValues=false与stored=false还能在结果中看到字段

A: 未知


<a id="org129c4de"></a>

### Q: 从 example/example-DIH/solr/ 中复制solr.xml 作为cloud的配置文件无法生效

A: 因为默认的配置文件里面有 standalone="yes" 及不使用集群方式


<a id="org93c7b8a"></a>

### Q: 为什么找不到 Can't find resource 'schema.xml'

A: example 文件夹中的配置文件为 managed-schema 需要改成 schema.xml 上传才行

