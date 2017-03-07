<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#orgfdd7c34">1. solrCloud</a>
<ul>
<li><a href="#org7aa9a5f">1.1. features</a></li>
<li><a href="#org3c4d773">1.2. 相关概念</a>
<ul>
<li><a href="#org26a801d">1.2.1. Node</a></li>
<li><a href="#orgc3d2b1a">1.2.2. Cluster</a></li>
<li><a href="#org023db8b">1.2.3. Collection</a></li>
<li><a href="#org0c87e47">1.2.4. Config Set</a></li>
<li><a href="#org57107cf">1.2.5. Leader</a></li>
<li><a href="#orge465beb">1.2.6. Replica</a></li>
<li><a href="#org1d112f7">1.2.7. Shard</a></li>
<li><a href="#orgb826866">1.2.8. Zookeeper</a></li>
</ul>
</li>
<li><a href="#orgec630f7">1.3. 配置外部 ZooKeeper</a>
<ul>
<li><a href="#org97dd11b">1.3.1. 一个实例</a></li>
<li><a href="#org546db7a">1.3.2. 集群</a></li>
<li><a href="#org77358f1">1.3.3. 通过zookeeper管理配置文件</a></li>
<li><a href="#org7c40701">1.3.4. 添加 node</a></li>
<li><a href="#orgf497294">1.3.5. Collections API</a></li>
</ul>
</li>
<li><a href="#org61da28a">1.4. Run Examples</a>
<ul>
<li><a href="#orgbd27086">1.4.1. 通过 bin/solr restart 可以重启节点</a></li>
<li><a href="#org2b20ccc">1.4.2. 向集群中添加一个节点</a></li>
</ul>
</li>
</ul>
</li>
</ul>
</div>
</div>
\#+TITLE SolrCloud


<a id="orgfdd7c34"></a>

# solrCloud

server/solr


<a id="org7aa9a5f"></a>

## features

1.  集中式配置管理
2.  自动化负载均衡和故障切换
3.  ZooKeeper 整合


<a id="org3c4d773"></a>

## 相关概念


<a id="org26a801d"></a>

### Node

solr实例


<a id="orgc3d2b1a"></a>

### Cluster

可以包含多个Collection，由一个或者多个node组成


<a id="org023db8b"></a>

### Collection

在SolrCloud集群中逻辑意义上的完整的索引, 可以分到多个Shards上


<a id="org0c87e47"></a>

### Config Set

Solr Core提供服务必须的一组配置文件


<a id="org57107cf"></a>

### Leader

赢得选举的Shard replicas


<a id="orge465beb"></a>

### Replica

Shard的一个拷贝


<a id="org1d112f7"></a>

### Shard

Collection的逻辑分片。一个shard上面一个leader replica


<a id="orgb826866"></a>

### Zookeeper

Zookeeper提供分布式锁功能，对SolrCloud是必须的。它处理Leader选举。Solr可以以内嵌的Zookeeper运行，但是建议用独立的，并且最好有3个以上的主机。 


<a id="orgec630f7"></a>

## 配置外部 ZooKeeper

**需要多少Zookeeper** 想要挂掉F个机器时还能正常提供服务，就需要 2\*F+1 台机器
下载地址： <http://zookeeper.apache.org/releases.html>


<a id="org97dd11b"></a>

### 一个实例

-   <ZOOKEEPER<sub>HOME</sub>>/conf/zoo.cfg

    # 一个滴答（时间单位， 毫秒）
    tickTime=2000 
    # 数据文件夹
    dataDir=/var/lib/zookeeper
    # 端口号
    clientPort=2181


<a id="org546db7a"></a>

### 集群

1.  配置文件

    -   zoo.cfg
        
            dataDir=/var/lib/zookeeperdata/1
            clientPort=2181
            # 初始化连接最大忍受的滴答次数
            initLimit=5
            # leader 与 follower 发送消息最大的等待时间
            syncLimit=2
            # server.{第几号服务器}={ip地址}:{服务器与leader交换信息的端口}:{leader服务器挂掉之后，选举信息通信的端口}
            server.1=localhost:2888:3888
            server.2=localhost:2889:3889
            server.3=localhost:2890:3890
    
    -   zoo2.cfg
        
            tickTime=2000
            dataDir=~/self/zoo/zoodata/2
            clientPort=2182
            initLimit=5
            syncLimit=2
            server.1=localhost:2888:3888
            server.2=localhost:2889:3889
            server.3=localhost:2890:3890
    
    -   zoo3.cfg
        
            tickTime=2000
            dataDir=~/self/zoo/zoodata/3
            clientPort=2183
            initLimit=5
            syncLimit=2
            server.1=localhost:2888:3888
            server.2=localhost:2889:3889
            server.3=localhost:2890:3890
    
    -   myid file
        
            mkdir -p zoodata/{1,2,3}
            echo 1 > 1/myid
            echo 2 > 2/myid
            echo 3 > 3/myid
    
    -   启动三个zookeeper
    
    cd <ZOOKEEPER<sub>HOME</sub>>
    bin/zkServer.sh start zoo.cfg
    bin/zkServer.sh start zoo2.cfg
    bin/zkServer.sh start zoo3.cfg
    
    -   引用外部zookeeper
    
    bin/solr start -e cloud -z localhost:2181,localhost:2182,localhost:2183 -noprompt
    
        ➜  zoo bin/zkServer.sh status zoo.cfg
        ZooKeeper JMX enabled by default
        Using config: /Users/wudanyang/self/zoo/bin/../conf/zoo.cfg
        Mode: follower
        ➜  zoo bin/zkServer.sh status zoo2.cfg
        ZooKeeper JMX enabled by default
        Using config: /Users/wudanyang/self/zoo/bin/../conf/zoo2.cfg
        Mode: leader
        ➜  zoo bin/zkServer.sh status zoo3.cfg
        ZooKeeper JMX enabled by default
        Using config: /Users/wudanyang/self/zoo/bin/../conf/zoo3.cfg
        Mode: follower


<a id="org77358f1"></a>

### 通过zookeeper管理配置文件

上传配置文件
sh zkcli.sh -cmd upconfig -zkhost <host:port> -confname <name for configset> -solrhome <solrhome> -confdir <path to directory with configset>
cd *Users/wudanyang/self/solr/server/scripts/cloud-scripts
sh zkcli.sh -cmd upconfig -zkhost localhost:2181 -confname yang -confdir ..*../../server/solr/configsets/basic<sub>configs</sub>/conf


<a id="org7c40701"></a>

### 添加 node

-   zkServer.sh start \*.cfg
-   bin/solr start -cloud -s <conf path> -p 8987 -z localhost:2181 # 添加一个节点,配置文件夹中必须包含一个solr.xml文件
-   bin/solr start -cloud -s confs/cloud/conf/ -p 8984 -z localhost:2181,localhost:2182,localhost:2183
-   zkServer.sh stop


<a id="orgf497294"></a>

### Collections API

创建多个shard需要多个node
nodeNum = shardNum \* replicationFactorNum

-   <http://localhost:8983/solr/admin/collections?action=CREATE&name=yang&numShards=1&replicationFactor=3&collection.configName=yang>
-   <http://localhost:8983/solr/admin/collections?action=RELOAD&name=yang_test2>


<a id="org61da28a"></a>

## Run Examples


<a id="orgbd27086"></a>

### 通过 bin/solr restart 可以重启节点

bin/solr restart -c -p 8983 -s example/cloud/node1/solr
-c 启动solrcloud模式
-p 指定端口
-h 指定host
bin/solr restart -c -p 7574 -z localhost:9983 -s example/cloud/node2/solr
-z zookeeper服务器地址


<a id="org2b20ccc"></a>

### 向集群中添加一个节点

mkdir <solr.home for new solr node>
cp <existing solr.xml path> <new solr.home>
bin/solr start -cloud -s solr.home/solr -p <port num> -z <zk hosts string>
bin/solr start -cloud -s <conf path> -p 8987 -z localhost:2181 # 添加一个节点,配置文件夹中必须包含一个solr.xml文件

也可以通过以下命令,将solr.xml上传到zookeeper，这样就不用总是复制solr.xml到新的节点
zkcli.sh -zkhost localhost:2181 -cmd putfile /solr.xml /path/to/solr.xml

1.  example

    mkdir -p example/cloud/node3/solr
    cp server/solr/solr.xml example/cloud/node3/solr
    第一次以cloud模式启动时会启动一个zookeeper服务器端口号是cloud端口号加上1000
    bin/solr start -cloud -s example/cloud/node3/solr -p 8987 -z localhost:9983

