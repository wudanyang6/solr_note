<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#org1a41c38">1. Quick Start</a>
<ul>
<li><a href="#orge372aff">1.1. Prerequisite</a>
<ul>
<li><a href="#org69b6de0">1.1.1. Java Run Environment(JRE)</a></li>
</ul>
</li>
<li><a href="#org8e26faf">1.2. Installing Solr</a></li>
<li><a href="#org511b44b">1.3. Running Solr</a></li>
<li><a href="#orgb9bb5f1">1.4. Create a Core(Collection if on Cloud)</a></li>
<li><a href="#org46c9c04">1.5. Add Document</a></li>
<li><a href="#orge8e8724">1.6. Ask Question</a></li>
</ul>
</li>
<li><a href="#org9ab17e5">2. Using the Solr Administration User Interface</a>
<ul>
<li><a href="#orgb568328">2.1. 访问</a></li>
<li><a href="#org148bcaf">2.2. 获取帮助</a></li>
<li><a href="#org2eee59e">2.3. Logging</a></li>
<li><a href="#org1b0401b">2.4. Cloud</a>
<ul>
<li><a href="#orgab8f045">2.4.1. Tree</a></li>
<li><a href="#orgd516f38">2.4.2. graph</a></li>
<li><a href="#org1eb4a5b">2.4.3. Dump</a></li>
</ul>
</li>
<li><a href="#orge61f719">2.5. Collections / Core Admin</a></li>
<li><a href="#orga0cb93c">2.6. Thread Dump</a></li>
<li><a href="#orgbe9fba0">2.7. Collection-Specific Tools(只有在cloud下才能看到)</a>
<ul>
<li><a href="#org3c86dbb">2.7.1. Analysis</a></li>
<li><a href="#orge77b29f">2.7.2. Documents</a></li>
<li><a href="#org61c250b">2.7.3. Files</a></li>
<li><a href="#org79a8485">2.7.4. Stream</a></li>
<li><a href="#org89a0a53">2.7.5. Schema</a></li>
</ul>
</li>
<li><a href="#orge9408cf">2.8. Core-Specific Tools</a>
<ul>
<li><a href="#org204a4a7">2.8.1. Ping</a></li>
<li><a href="#orgdf46fa0">2.8.2. Segment</a></li>
</ul>
</li>
</ul>
</li>
<li><a href="#org68c2672">3. Documents, Fields, and Schema Design</a>
<ul>
<li><a href="#orgde304ca">3.1. Overview</a>
<ul>
<li><a href="#org63ff9f6">3.1.1. 原理简介</a></li>
<li><a href="#org68aee62">3.1.2. Field Analysis</a></li>
<li><a href="#orgb6bbd4f">3.1.3. Schema File</a></li>
</ul>
</li>
<li><a href="#orgf6e55f4">3.2. Schema Detail</a>
<ul>
<li><a href="#orgfb3cc21">3.2.1. Solr Field Types</a></li>
<li><a href="#orga7b9b12">3.2.2. Defining Fields</a></li>
<li><a href="#orgd97519d">3.2.3. Copying Fields</a></li>
<li><a href="#org73e8c3e">3.2.4. Dynamic Fields</a></li>
<li><a href="#org21788e9">3.2.5. Other Elements</a></li>
<li><a href="#orgc5e8901">3.2.6. Schema API</a></li>
<li><a href="#org496966b">3.2.7. Putting the Pieces Together</a></li>
</ul>
</li>
</ul>
</li>
<li><a href="#org8bfd7aa">4. <span class="todo TODO">TODO</span> Using Analyzers, Tokenizers, and Filters</a>
<ul>
<li><a href="#org1f230a4">4.1. </a></li>
</ul>
</li>
<li><a href="#org26a5c2c">5. Indexing and Basic Data Operations</a>
<ul>
<li><a href="#org9bedbb1">5.1. Post Tool</a>
<ul>
<li><a href="#orgba833b6">5.1.1. bin/post</a></li>
<li><a href="#org1c10e9b">5.1.2. SimplePostTool</a></li>
</ul>
</li>
<li><a href="#org25aa29c">5.2. Uploading Data with Index Handlers</a></li>
<li><a href="#org474caff">5.3. <span class="todo TODO">TODO</span> Uploading Data with Solr Cell using Apache Tika</a></li>
</ul>
</li>
<li><a href="#org18a923f">6. Search</a>
<ul>
<li><a href="#org377279d">6.1. Overview</a>
<ul>
<li><a href="#org89dd01f">6.1.1. 输入查询语句</a></li>
<li><a href="#org42ea2de">6.1.2. 查询语句被 <b>request handler</b> 处理 (此插件定义了solr处理请求的逻辑)</a></li>
<li><a href="#org75316ad">6.1.3. 调用 <b>query parser</b> (解析器解释查询的条件和参数)</a></li>
<li><a href="#orgbf8bace">6.1.4. *filter query*(fq) (filter query 会开辟一块单独的缓存，这种策略对性能提升很大)</a></li>
<li><a href="#org2fdd0a7">6.1.5. 指定特定的条件高亮</a></li>
<li><a href="#org66a782b">6.1.6. 返回结果可以有一个小片段，像是谷歌的搜索</a></li>
<li><a href="#org026bdd4">6.1.7. 对结果分组</a></li>
<li><a href="#org851290c">6.1.8. MoreLikeThis</a></li>
<li><a href="#orgf13c25b">6.1.9. response writer (返回结果的形式)</a></li>
</ul>
</li>
<li><a href="#org92fc327">6.2. 通用查询语句</a>
<ul>
<li><a href="#org83ec444">6.2.1. defType:</a></li>
<li><a href="#org1035f90">6.2.2. sort:</a></li>
<li><a href="#orgf65f486">6.2.3. start:</a></li>
<li><a href="#org26785e2">6.2.4. rows:</a></li>
<li><a href="#org7ed95c8">6.2.5. fq:</a></li>
<li><a href="#org649d8af">6.2.6. fl:</a></li>
<li><a href="#orgff423e1">6.2.7. debug:</a></li>
<li><a href="#org5f07b4c">6.2.8. explainOther:</a></li>
<li><a href="#orgfb10da1">6.2.9. timeAllowed：</a></li>
<li><a href="#orgc165c77">6.2.10. omitHeader:</a></li>
<li><a href="#orgccce01b">6.2.11. wt:</a></li>
<li><a href="#org1326253">6.2.12. cache=false:</a></li>
<li><a href="#orgfce7a0b">6.2.13. logParamsList(version &gt;= 4.7):</a></li>
<li><a href="#org6d8a8ff">6.2.14. echoParams:</a></li>
</ul>
</li>
<li><a href="#org4b98d05">6.3. The Standard Query Parser (lucene parser)</a>
<ul>
<li><a href="#org44bcfd0">6.3.1. q</a></li>
<li><a href="#org21fea94">6.3.2. q.op</a></li>
<li><a href="#org0e2e6e7">6.3.3. df</a></li>
</ul>
</li>
<li><a href="#orgb42340f">6.4. <span class="todo TODO">TODO</span> The DisMax Query Parser</a>
<ul>
<li><a href="#org520f8fc">6.4.1. Parameters</a></li>
</ul>
</li>
<li><a href="#org705ea35">6.5. Faceting</a>
<ul>
<li><a href="#org837e39e">6.5.1. General Parameters</a></li>
<li><a href="#orgb7018b8">6.5.2. Field-Value Faceting Parameters</a></li>
<li><a href="#org3ff07e9">6.5.3. facet.pivot</a></li>
</ul>
</li>
<li><a href="#org0332cf5">6.6. Highlighter</a>
<ul>
<li><a href="#orgfe69e0b">6.6.1. Standard Highlighter</a></li>
</ul>
</li>
</ul>
</li>
<li><a href="#org7d878b0">7. solrCloud</a>
<ul>
<li><a href="#org513c7ad">7.1. features</a></li>
<li><a href="#org8398698">7.2. 相关概念</a>
<ul>
<li><a href="#org98545f8">7.2.1. Node</a></li>
<li><a href="#org8e16ae2">7.2.2. Cluster</a></li>
<li><a href="#org5050b19">7.2.3. Collection</a></li>
<li><a href="#org01425aa">7.2.4. Config Set</a></li>
<li><a href="#orgee662c0">7.2.5. Leader</a></li>
<li><a href="#org462c031">7.2.6. Replica</a></li>
<li><a href="#org6e59f6d">7.2.7. Shard</a></li>
<li><a href="#org2fb1de6">7.2.8. Zookeeper</a></li>
</ul>
</li>
<li><a href="#org365f153">7.3. 配置外部 ZooKeeper</a>
<ul>
<li><a href="#orge445b25">7.3.1. 一个实例</a></li>
<li><a href="#org95ac737">7.3.2. 集群</a></li>
<li><a href="#orgc822580">7.3.3. 通过zookeeper管理配置文件</a></li>
<li><a href="#org2f76ba5">7.3.4. 添加 node</a></li>
<li><a href="#org6f3a646">7.3.5. Collections API</a></li>
</ul>
</li>
<li><a href="#org8fb563c">7.4. Run Examples</a>
<ul>
<li><a href="#org3fe67d8">7.4.1. 通过 bin/solr restart 可以重启节点</a></li>
<li><a href="#org712ee03">7.4.2. 向集群中添加一个节点</a></li>
</ul>
</li>
</ul>
</li>
<li><a href="#org8adf343">8. Issues</a>
<ul>
<li><a href="#org1b77193">8.1. 学习时遇到的问题</a>
<ul>
<li><a href="#org99efb79">8.1.1. Q: ZooKeeper JMX enabled by default Using config: <i>Users/wudanyang/self/zoo/bin</i>../conf/zoo.cfg Error contacting service. It is probably not running.</a></li>
<li><a href="#orgd4e224d">8.1.2. Q: ZooKeeper 执行 bin/zkServer.sh status 说未启动</a></li>
<li><a href="#org9762773">8.1.3. Q: SolrCore Initialization Failures</a></li>
<li><a href="#org2ccda8d">8.1.4. Q: 通过api创建collection时, 返回localhost未返回任何数据</a></li>
<li><a href="#org3d0f69e">8.1.5. Q: Cannot create collection tinycollection. Value of maxShardsPerNode is 1, and the number of live nodes is 4. This allows a maximum of 4 to be created. Value of numShards is 2 and value of replicationFactor is 3. This requires 6 shards to be created (higher than the allowed number)&lt;/str&gt;</a></li>
<li><a href="#org9c87174">8.1.6. Q: 在zookeeper中找不到配置文件</a></li>
<li><a href="#org008e8be">8.1.7. Q: 为何在6.*以上的solr中store=false 仍然能看到字段被返回了</a></li>
<li><a href="#org154c8db">8.1.8. Q: int类型为何docValues=false与stored=false还能在结果中看到字段</a></li>
<li><a href="#org14d1849">8.1.9. Q: 从 example/example-DIH/solr/ 中复制solr.xml 作为cloud的配置文件无法生效</a></li>
<li><a href="#org055d119">8.1.10. Q: 为什么找不到 Can't find resource 'schema.xml'</a></li>
</ul>
</li>
<li><a href="#orgf629ff2">8.2. 公司系统发现的问题</a></li>
</ul>
</li>
<li><a href="#org231e13f">9. Cache</a></li>
</ul>
</div>
</div>


<a id="org1a41c38"></a>

# Quick Start


<a id="orge372aff"></a>

## Prerequisite


<a id="org69b6de0"></a>

### Java Run Environment(JRE)

-   version >= 1.8

    java -version


<a id="org8e26faf"></a>

## Installing Solr

    wget http://lucene.apache.org/solr/
    cd /path/to/solr_arch
    tar zxf solr-x.y.z.tgz


<a id="org511b44b"></a>

## Running Solr

    bin/solr start
    bin/solr -help
    # 指定命令的帮助文档
    bin/solr start -help
    
    # 前端开启Foreground
    bin/solr start -f
    # 指定端口 (默认是8983)
    bin/solr start -p 8984
    bin/solr stop [-p 8983 | -all]
    
    # 启动示例
    bin/solr -e techproducts [techproducts, dih, schemaless, and cloud.]
    
    bin/solr status

➜  solr bin/solr -e techproducts

    ➜  solr bin/solr -e techproducts
    Solr home directory /Users/wudanyang/self/solr/example/techproducts/solr already exists.
    
    Starting up Solr on port 8983 using command:
    bin/solr start -p 8983 -s "example/techproducts/solr"
    
    Archiving 1 old GC log files to /Users/wudanyang/self/solr/example/techproducts/solr/../logs/archived
    Archiving 1 console log files to /Users/wudanyang/self/solr/example/techproducts/solr/../logs/archived
    Rotating solr logs, keeping a max of 9 generations
    Waiting up to 180 seconds to see Solr running on port 8983 [\]
    Started Solr server on port 8983 (pid=28473). Happy searching!
    
    
    Copying configuration to new core instance directory:
    /Users/wudanyang/self/solr/example/techproducts/solr/techproducts
    
    Creating new core 'techproducts' using command:
    http://localhost:8983/solr/admin/cores?action=CREATE&name=techproducts&instanceDir=techproducts
    
    {
      "responseHeader":{
        "status":0,
        "QTime":2036},
      "core":"techproducts"}
    
    
    Indexing tech product example docs from /Users/wudanyang/self/solr/example/exampledocs
    SimplePostTool version 5.0.0
    Posting files to [base] url http://localhost:8983/solr/techproducts/update using content-type application/xml...
    POSTing file gb18030-example.xml to [base]
    POSTing file hd.xml to [base]
    POSTing file ipod_other.xml to [base]
    POSTing file ipod_video.xml to [base]
    POSTing file manufacturers.xml to [base]
    POSTing file mem.xml to [base]
    POSTing file money.xml to [base]
    POSTing file monitor.xml to [base]
    POSTing file monitor2.xml to [base]
    POSTing file mp500.xml to [base]
    POSTing file sd500.xml to [base]
    POSTing file solr.xml to [base]
    POSTing file utf8-example.xml to [base]
    POSTing file vidcard.xml to [base]
    14 files indexed.
    COMMITting Solr index changes to http://localhost:8983/solr/techproducts/update...
    Time spent: 0:00:00.601
    
    Solr techproducts example launched successfully. Direct your Web browser to http://localhost:8983/solr to visit the Solr Admin UI


<a id="orgb9bb5f1"></a>

## Create a Core(Collection if on Cloud)

-   上面运行的是示例文件,创建自己Core用来索引和搜索文档
-   Core与Solr的关系跟软件与操作系统关系相似
-   每个core有自身的配置文件及数据

    bin/solr create -c <name>
    bin/solr create -help

    ➜  solr bin/solr create -help
    Usage: solr create [-c name] [-d confdir] [-n configName] [-shards \#] [-replicationFactor \#] [-p port]
      Create a core or collection depending on whether Solr is running in standalone (core) or SolrCloud
      mode (collection). In other words, this action detects which mode Solr is running in, and then takes
      the appropriate action (either create_core or create_collection).


<a id="org46c9c04"></a>

## Add Document

schema 决定了文档的结构

    ➜  solr bin/post -help
    
    Usage: post -c <collection> [OPTIONS] <files|directories|urls|-d ["...",...]>
        or post -help
    
      collection name defaults to DEFAULT_SOLR_COLLECTION if not specified
    
    OPTIONS
    =======
      Solr options:
        -url <base Solr update URL> (overrides[包括] collection, host, and port)
        -host <host> (default: localhost)
        -p or -port <port> (default: 8983)
        -commit yes|no (default: yes)
        -u or -user <user:pass> (sets BasicAuth credentials)
    
      Web crawl options:
        -recursive <depth> (default: 1)
        -delay <seconds> (default: 10)
    
      Directory crawl options:
        -delay <seconds> (default: 0)
    
      stdin/args options:
        -type <content/type> (default: application/xml)
    
      Other options:
        -filetypes <type>[,<type>,...] (default: xml,json,jsonl,csv,pdf,doc,docx,ppt,pptx,xls,xlsx,odt,odp,ods,ott,otp,ots,rtf,htm,html,txt,log)
        -params "<key>=<value>[&<key>=<value>...]" (values must be URL-encoded; these pass through to Solr update request)
        -out yes|no (default: no; yes outputs Solr response to console)
        -format solr (sends application/json content as Solr commands to /update instead of /update/json/docs)
    
    
    Examples:
    
    -*- JSON file: bin/post -c wizbang events.json
    -*- XML files: bin/post -c records article*.xml
    -*- CSV file: bin/post -c signals LATEST-signals.csv
    -*- Directory of files: bin/post -c myfiles ~/Documents
    -*- Web crawl: bin/post -c gettingstarted http://lucene.apache.org/solr -recursive 1 -delay 1
    -*- Standard input (stdin): echo '{commit: {}}' | bin/post -c my_collection -type application/json -out yes -d
    -*- Data as string: bin/post -c signals -type text/csv -out yes -d $'id,value\n1,0.47'


<a id="orge8e8724"></a>

## Ask Question

-   url example:
    -   <http://localhost:8983/solr/gettingstarted/select?q=video>
        -   host: localhost
        -   port: 8983
        -   app name: solr
        -   request handler: select
        -   query: q
    -   <http://localhost:8983/solr/gettingstarted/select?q=video&fl=id,name,price>
        -   fl: 返回的字段
    -   <http://localhost:8983/solr/gettingstarted/select?q=name:black>
        -   q=name:black      name值为black的文档
    -   <http://localhost:8983/solr/gettingstarted/select?q=price:[0%20TO%20400]&fl=id,name,price>
        -   price:[0%20TO%20400]    范围查询 链接部分需要 urlencode
    -   <http://localhost:8983/solr/gettingstarted/select?q=price:[0%20TO%20400]&fl=id,name,price&facet=true&facet.field=cat>
        -   facet=true 相当于分组 (facet翻译：方面、侧面、宝石切面。意思是根据facet进行分类[分成几个侧面])
        -   facet.field=cat
        -   facet 的字段必须被索引
        -   可以根据分组进行再次查询
            -   <http://localhost:8983/solr/gettingstarted/select?q=price:0%20TO%20400&fl=id,name,price&facet=true&facet.field=cat&fq=cat:software>
-   documention
    -   responseHeader
        
            <lst name="responseHeader">
            <int name="status">0</int>
            <int name="QTime">85</int>
            <lst name="params">
            <str name="q">video</str>
            </lst>
            </lst>
    -   result 包括一个或者多个doc标签
        
            <result name="response" numFound="3" start="0">xml
            <doc>xml
            <str name="id">MA147LL/A</str>xml
            <arr name="name">xml
            <str>Apple 60 GB iPod with Video Playback Black</str>xml
            </arr>xml
            <arr name="manu">xml
            ...
    -   facet\_counts
        
            <lst name="facet_counts">
              <lst name="facet_queries"/>
              <lst name="facet_fields">
              <lst name="cat">
              <int name="electronics">9</int>
              <int name="connector">2</int>
              <int name="hard drive">2</int>
              <int name="memory">2</int>
              <int name="search">2</int>
              <int name="software">2</int>
              <int name="camera">1</int>
              <int name="copier">1</int>
              <int name="electronics and stuff2">1</int>
              <int name="multifunction printer">1</int>
              <int name="music">1</int>
              <int name="printer">1</int>
              <int name="scanner">1</int>
              <int name="currency">0</int>
              <int name="electronics and computer1">0</int>
              <int name="graphics card">0</int>
              </lst>
              </lst>
              <lst name="facet_ranges"/>
              <lst name="facet_intervals"/>
              <lst name="facet_heatmaps"/>
              </lst>


<a id="org9ab17e5"></a>

# Using the Solr Administration User Interface


<a id="orgb568328"></a>

## 访问

<http://hostname:port/solr>


<a id="org148bcaf"></a>

## 获取帮助

底部链接

-   帮助文档
-   issue tracker
-   IRC 聊天室
-   社区论坛
-   查询语句的语法


<a id="org2eee59e"></a>

## Logging

-   黄色高亮的有记录日志的能力
-   黑体字部分不受root影响


<a id="org1b0401b"></a>

## Cloud


<a id="orgab8f045"></a>

### Tree

显示zookeeper内部数据


<a id="orgd516f38"></a>

### graph

显示collection的分片信息


<a id="org1eb4a5b"></a>

### Dump

获取一份ZooKeeper中的solr数据快照。（帮助调试）


<a id="orge61f719"></a>

## Collections / Core Admin

一个实例时叫CoreAdmin 多个实例Collection


<a id="orga0cb93c"></a>

## Thread Dump

监视当前活动的线程，绿色对号是RUNNABLE
鼠标放到名字上会有状态显示:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">name</td>
<td class="org-left">desc</td>
</tr>


<tr>
<td class="org-left">NEW</td>
<td class="org-left">未启动</td>
</tr>


<tr>
<td class="org-left">RUNNABLE</td>
<td class="org-left">在jvm中运行</td>
</tr>


<tr>
<td class="org-left">BLOCKED</td>
<td class="org-left">阻塞</td>
</tr>


<tr>
<td class="org-left">WAITING</td>
<td class="org-left">等待</td>
</tr>


<tr>
<td class="org-left">TIMED\_WAITING</td>
<td class="org-left">有时间的等待</td>
</tr>


<tr>
<td class="org-left">TERMINATED</td>
<td class="org-left">退出</td>
</tr>
</tbody>
</table>


<a id="orgbe9fba0"></a>

## Collection-Specific Tools(只有在cloud下才能看到)


<a id="org3c86dbb"></a>

### Analysis

分析查询语句


<a id="orge77b29f"></a>

### Documents

更新数据


<a id="org61c250b"></a>

### Files

configuration files | solrCloud展示的是ZooKeeper中的配置文件

1.  solrconfig.xml
    -   定义了solr如何索引内容和响应请求
2.  Schema 定义数据类型
    -   文档字段


<a id="org79a8485"></a>

### Stream

raw版本的query界面


<a id="org89a0a53"></a>

### Schema

1.  选择字段
2.  load term info 加载根据条件取出的前N个的信息(只从Collection的一个Core取数据作为样本)


<a id="orge9408cf"></a>

## Core-Specific Tools


<a id="org204a4a7"></a>

### Ping

查看是否能访问

-   <http://localhost:8983/solr/><core-name>/admin/ping
-   <http://localhost:8983/solr/gettingstarted_shard1_replica1/admin/ping?_=1481531966193&ts=1481531966193&wt=json>


<a id="orgdf46fa0"></a>

### Segment

当前核心的片段数据


<a id="org68c2672"></a>

# Documents, Fields, and Schema Design


<a id="orgde304ca"></a>

## Overview


<a id="org63ff9f6"></a>

### 原理简介

-   feed in (indexing or updating)
-   ask questions (query)


<a id="org68aee62"></a>

### Field Analysis

告诉solr如何处理字段，如需要忽略的字段与转换形式（a,the,an,Running=>run）


<a id="orgb6bbd4f"></a>

### Schema File

告诉solr如何对输入的文档简历索引

-   默认为\*managed-schema\*文件
-   Cloud模式没有此文件，只能通过api或者cloud-ui看到
-   api方式修改只能修改\*managed schema\*指定的文件
-   solrCloud不通过api方式修改schema只能通过 upconfig 和 downconfg 让ZooKeeper管理配置文件


<a id="orgf6e55f4"></a>

## Schema Detail

server/


<a id="orgfb3cc21"></a>

### Solr Field Types

1.  TODO Field Type Definitions and Properties（完善属性定义）

    1.  字段类型定义可以包含四种类型
        -   name 必须
        -   class 必须
        -   如果字段类型是TextField，可以加上对field analysis
        -   字段类型的属性，取决于class
    2.  类型定义
        -   放在fieldType标签中
        -   可以用type标签分组
    3.  Field Type Properties
        -   <fieldType name="date" class="solr.TrieDateField" sortMissingLast="true" omitNorms="true"/>
        -   属性被分成三种
            1.  针对field type的class的属性
            2.  常规属性
                -   name
                -   class
                -   positionIncrementGap (对multivalue field 处理时，给两个field的词人为加上distance)
                -   autoGeneratePhraseQueries
                -   docValuesFormat (docValues的格式)
                -   postingsFormat
            3.  字段默认属性（替换继承的默认属性）
                -   indexed (是否建立索引)
                -   stored (是否存储内容)
                -   docValues ( 可以提升如排序,分面,高亮的性能)
                -   sortMissingFirst/sortMissingLast
                -   multiValued (多值)
    4.  例子:
    
        <fieldType name="ancestor_path" class="solr.TextField">
          <analyzer type="index">
            <tokenizer class="solr.KeywordTokenizerFactory"/>
          </analyzer>
          <analyzer type="query">
            <tokenizer class="solr.PathHierarchyTokenizerFactory" delimiter="/"/>
          </analyzer>
        </fieldType>

2.  TODO Field Types Included with Solr

3.  TODO Working with Currencies and Exchange Rates

4.  TODO Working with Dates

5.  TODO Working with Enum Fields

6.  TODO Working with External Files and Processes


<a id="orga7b9b12"></a>

### Defining Fields

1.  example

    -   <field name="price" type="float" default="0.0" indexed="true" stored="true"/>

2.  Field Properties

    -   name (must)
    -   type (must)
    -   default (optional)

3.  TODO Optional Field Type Override Properties

    会覆盖掉 fieldType 属性的属性


<a id="orgd97519d"></a>

### Copying Fields

-   为一个数据应用多种不同的字段类型
-   需要搜索多个字段, 可以通过\*copyField\*组成一个字段，然后配置成默认搜索此字段。
-   使用\*copyField\*会造成索引数据的增长
-   source和dest开头或者结尾可以有\*表示匹配所有(表示通配符)

1.  主要字段

    -   source 被复制的字段名称
    -   dest 复制到的名称
    -   maxChars 限制从source最多复制的字符 (想要控制index大小时有用)

2.  example

        <copyField source="cat" dest="text" maxChars="30000" />
        <copyField source="*_t" dest="text" maxChars="25000" />
    
    如果text中有数据，那么cat中的内容将会添加到text中。
    
    如果dest的source是多个值组成的，或者dest有多个source需要把dest字段设置成multivalued="true"
    
        <schema name="eshequn.post.db_post.0" version="1.1" xmlns:xi="http://www.w3.org/2001/XInclude">  
          <fields>  
            <field name="title" type="text" indexed="true" stored="false" />  
            <field name="content" type="text" indexed="true" stored="false" />  
            <field name="tc" type="text" indexed="true" stored="false" multiValued="true"/>  
          </fields>  
          <copyField source="title" dest="tc" />  
          <copyField source="content" dest="tc" />  
        <
        /schema>


<a id="org73e8c3e"></a>

### Dynamic Fields

顾名思义，动态字段。

    <dynamicField name="*_i" type="int" indexed="true" stored="true"/>


<a id="org21788e9"></a>

### Other Elements

1.  Unique Key

    指定文档的唯一标志(更新文档的时候有用)

2.  Default Search Field & Query Operator

    -   <defaultSearchField/> 已经被df参数取代
    -   <solrQueryParserdefaultOperator="OR"/> 被q.op取代

3.  Similarity

    用来在搜索时获取文档的相关度(score)。自定义评分器。
    
    -   每个文档只能有一个全局的Similarity
    -   默认行为BM25SimilarityFactory
    -   通过<similarity/> 标签可以覆盖默认行为
    -   可以通过两种形式实现
    -   ![img](//static.oschina.net/uploads/space/2012/0327/191046_bwnq_100580.png)
    
        <similarity class="solr.BM25SimilarityFactory"/>
        <similarity class="solr.DFRSimilarityFactory">
            <str name="basicModel">P</str>
            <str name="afterEffect">L</str>
            <str name="normalization">H2</str>
            <float name="c">7</float>
        </similarity>


<a id="orgc5e8901"></a>

### Schema API

提供一种通过http请求来读取和修改schema的方式

-   schema修改之后只会改变后来的文档索引形式，不会改变之前的索引文档。所以必须重新索引所有的文档
-   output format： json | xml
-   <http://><host>:<port>/solr/<collection\_name>/schema/

1.  API Entry Points

    -   /schema: retrieve the schema, or modify the schema to add, remove, or replace fields, dynamic fields, copy fields, or field types
    -   /schema/fields: retrieve information about all defined fields or a specific named field
    -   /schema/dynamicfields: retrieve information about all dynamic field rules or a specific named dynamic rule
    -   /schema/fieldtypes: retrieve information about all field types or a specific field type
    -   /schema/copyfields: retrieve information about copy fields
    -   /schema/name: retrieve the schema name
    -   /schema/version: retrieve the schema version
    -   /schema/uniquekey: retrieve the defined uniqueKey
    -   /schema/similarity: retrieve the global similarity definition
    -   /schema/solrqueryparser/defaultoperator: retrieve the default operator

2.  Modify the Schema

            "add-field":{ "name":"sell-by", "type":"tdate", "stored":true } 
        }' http://localhost:8983/solr/gettingstarted/schema
    
    1.  Schema Changes among Replicas
    
        在一个复制集上做的更改会改到其他的复制集上面

3.  Retrieve Schema Information

        curl http://localhost:8983/solr/gettingstarted/schema?wt=json
        curl http://localhost:8983/solr/gettingstarted/schema?wt=xml
        curl http://localhost:8983/solr/gettingstarted/schema?wt=schema.xml
        curl http://localhost:8983/solr/gettingstarted/schema/fields?wt=json[fl=string,string
        &includeDynamic=bool&showDefaults=bool]


<a id="org496966b"></a>

### Putting the Pieces Together

1.  Choosing Appropriate Numeric Types

    1.  一般情况下 使用
        -   TrieIntField
        -   TrieLongField
        -   TrieFloatField
        -   TrieDoubleFiel
        -   precisionStep="0"
    2.  数字经常被指定范围
        -   precisionStep="8"

2.  Working With Text

    1.  通过使用一个txt field将所有字段汇总成一个搜索(用到了copyField)
    2.  通过copyField将一个字段作为不同的用处

3.  DocValues

    -   传统的index是一种倒排索引<sup><a id="fnr.1" class="footref" href="#fn.1">1</a></sup> 并且是term-to-document的list,对于使用term来搜索时，这种方式很快
    -   但是若是使用facet、sort、hightlight这些特性，就会很慢
    -   docvalues 是一种 面向列 的字段索引方式，并且使用了document-to-value的list
    -   indexed 和 docValues 只能指定一个为true
    -   只能开启以下几个类型的docValues
        1.  StrField
        2.  UUIDField
        3.  Trie\* numeric fields
        4.  date
        5.  EnumField

4.  TODO Using DocValues

5.  TODO Schemaless Mode


<a id="org8bfd7aa"></a>

# Using Analyzers, Tokenizers, and Filters


<a id="org1f230a4"></a>

## 


<a id="org26a5c2c"></a>

# Indexing and Basic Data Operations

三种常用的方式可以向solr index中填充数据

-   Solr Cell
-   xml file
-   Solr's Java Client API

填入的数据总是要包含多个字段，每个字段都有一个name和一个content
实验文件夹：example/exampledocs/


<a id="org9bedbb1"></a>

## Post Tool


<a id="orgba833b6"></a>

### bin/post

    bin/post -c gettingstarted example/films/films.json
    bin/post -h
    bin/post -c gettingstarted *.xml
    bin/post -c gettingstarted -p 8984 *.xml
    bin/post -c gettingstarted -d '<delete><id>42</id></delete>'
    bin/post -c gettingstarted *.csv
    bin/post -c gettingstarted -params "separator=%09" -type text/csv data.csv
    bin/post -c gettingstarted *.json
    bin/post -c gettingstarted a.pdf
    
    bin/post -p port -host host -c collection_name json_file.json
    # 自动检测文件夹中的文档类型，递归的进行索引数据
    bin/post -c gettingstarted afolder/
    bin/post -c gettingstarted -filetypes ppt,html afolder/
    # 索引一个带有密码的pdf 密码为SolrRocks
    bin/post -u solr:SolrRocks -c gettingstarted a.pdf


<a id="org1c10e9b"></a>

### SimplePostTool

java -jar example/exampledocs/post.jar -h


<a id="org25aa29c"></a>

## Uploading Data with Index Handlers

    curl -X POST -H 'Content-Type: application/json' 'http://localhost:8983/solr/my_collection/update' --data-binary ' [ { "id": "1", "title": "Doc 1" }, { "id": "2", "title": "Doc 2" } ]'
    # 指定文件
    curl 'http://localhost:8983/solr/techproducts/update?commit=true' --data-binary @example/exampledocs/books.json -H 'Content-type:application/json'


<a id="org474caff"></a>

## Uploading Data with Solr Cell using Apache Tika

导入多种不同的数据格式时有用，如二进制文件、word文档、pdf文档等。


<a id="org18a923f"></a>

# Search


<a id="org377279d"></a>

## Overview


<a id="org89dd01f"></a>

### 输入查询语句


<a id="org42ea2de"></a>

### 查询语句被 **request handler** 处理 (此插件定义了solr处理请求的逻辑)


<a id="org75316ad"></a>

### 调用 **query parser** (解析器解释查询的条件和参数)

1.  解析器的种类
    1.  Standard Query Parser (清晰)
    2.  DisMax (很少报错)
    3.  eDisMax (扩展版的DisMax，完全支持 lucene 查询语法)
2.  common query parameters  (支持全部的解析器)
3.  解析器输入种类
    1.  查询语句
    2.  对查询语句的微调参数
    3.  对查询结果展示的控制


<a id="orgbf8bace"></a>

### \*filter query\*(fq) (filter query 会开辟一块单独的缓存，这种策略对性能提升很大)

1.  Filter queries 只查询索引中存在的数据


<a id="org2fdd0a7"></a>

### 指定特定的条件高亮


<a id="org66a782b"></a>

### 返回结果可以有一个小片段，像是谷歌的搜索


<a id="org026bdd4"></a>

### 对结果分组

1.  faceting
    1.  facet 分组字段（对结果进行分组）
    2.  facet count 分组得到的结果的数量
    3.  constraints 分组得到的结果的值
    4.  breadcrumb 面包屑（已经应用的facet）
    5.  list 结果详情
2.  clustering


<a id="org851290c"></a>

### MoreLikeThis


<a id="orgf13c25b"></a>

### response writer (返回结果的形式)

1.  XML Response Writer
2.  JSON Response Writer


<a id="org92fc327"></a>

## 通用查询语句


<a id="org83ec444"></a>

### defType:

1.  选择查询解析器
2.  dismax/lucene
3.  defType=dismax


<a id="org1035f90"></a>

### sort:

1.  对返回结果排序，asc|desc
2.  可以对数字和字母排序
3.  排序规则
    1.  根据文档相关程度排序
    2.  或者是根据字段的值排序，这个字段的值要么被索引要么使用了\*DocValues\*
4.  单独字段排序：<field\_name>+(asc|desc)
5.  多字段排序：sort=<field name>+<direction>,<field name>+<direction>],&#x2026;


<a id="orgf65f486"></a>

### start:

-   初始位置


<a id="org26785e2"></a>

### rows:

-   相当于mysql中的limit


<a id="org7ed95c8"></a>

### fq:

1.  对结果过滤的条件
2.  对将要返回的文档过滤（不会影响score【猜测是相关度】）
3.  对复杂的query进行加速，因为会对fq进行的查询独立进行缓存
4.  fq参数可以出现多次
    1.  \`fq=popularity:[10 TO \*]&fq=section:0\` （当条件经常单独出现时）
    2.  \`fq=+popularity:[10 TO \*] +section:0\` (当条件经常单独出现时)
5.  url-encoding 参考地址 ：  <http://meyerweb.com/eric/tools/dencoder/>


<a id="org649d8af"></a>

### fl:

1.  设定返回结果的字段,用逗号或者空格分开
2.  stored="true" or docValues="true" or useDocValuesAsStored="true"(在docvalues模式开启时是默认的)
3.  字段可以是个函数 如：fl=id,title,product(price,popularity)
4.  别名：fl=id,sales\_price:price,secret\_sauce:prod(price,popularity),why\_score:[explain style=nl]


<a id="orgff423e1"></a>

### debug:

1.  返回额外的调试信息。
2.  debug=timing只返回时间信息.
3.  debug=results返回对返回结果的每个文档的解释。
4.  debug=all(true)将返回所有的调试信息。debugQuery=true


<a id="org5f07b4c"></a>

### explainOther:

-   q=supervillians&debugQuery=on&explainOther=id\\:juggernaut
-   返回调试信息
-   必须加上debugQuery=on否则不返回debug字段


<a id="orgfb10da1"></a>

### timeAllowed：

-   超过此时间之后，只会返回一部分数据


<a id="orgc165c77"></a>

### omitHeader:

-   不返回头部信息


<a id="orgccce01b"></a>

### wt:

-   返回结果的格式


<a id="org1326253"></a>

### cache=false:

-   停止缓存所有的查询和过滤条件的结果


<a id="orgfce7a0b"></a>

### logParamsList(version >= 4.7):

-   默认会记录所有的字段，logParamsList=param1,param2逗号分割的参数


<a id="org6d8a8ff"></a>

### echoParams:

在response header 中的 params 字段中显示所用到的查询字段

1.  explicit(默认)
2.  all
3.  none


<a id="org4b98d05"></a>

## The Standard Query Parser (lucene parser)

优点：直观，缺点：不能有语法错误


<a id="org44bcfd0"></a>

### q

查询语句，强制性

    http://localhost:8983/solr/techproducts/select?q=id:SP2514N
    q=*:* 查询全部,特殊情况

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">?</td>
<td class="org-left">匹配单个字符</td>
</tr>


<tr>
<td class="org-left">\*</td>
<td class="org-left">匹配多个字符</td>
</tr>


<tr>
<td class="org-left">~</td>
<td class="org-left">模糊搜索 roam~ 将会匹配foam，foams等</td>
</tr>


<tr>
<td class="org-left">~1</td>
<td class="org-left">模糊搜索 roam~ 将会匹配foam，不会匹配foams，因为foams改动了两个字</td>
</tr>


<tr>
<td class="org-left">"jakarta apache"~10</td>
<td class="org-left">两个词之间改动10个位置可以匹配到</td>
</tr>


<tr>
<td class="org-left">mod\_date:[20020101 TO 20030101]</td>
<td class="org-left">范围查询</td>
</tr>


<tr>
<td class="org-left">title:{Aida TO Smith}</td>
<td class="org-left">大括号表示不包含上下边界</td>
</tr>


<tr>
<td class="org-left">jakarta^4 apache</td>
<td class="org-left">boost factor 可以通过改变这个值改变查询时的相关度,可以小于1</td>
</tr>


<tr>
<td class="org-left">(description:blue OR color:blue)^=1.0 text:shoes</td>
<td class="org-left">将匹配括号中的语句的文档相关度设置成1</td>
</tr>


<tr>
<td class="org-left">title:"The Right Way" AND text:go</td>
<td class="org-left">指定字段查询</td>
</tr>


<tr>
<td class="org-left">title:"Do it right" AND go</td>
<td class="org-left">第二个字段直接查询默认搜索字段</td>
</tr>


<tr>
<td class="org-left">(AND/&&),(OR/ll),(+),(-),(NOT !)</td>
<td class="org-left">操作符</td>
</tr>


<tr>
<td class="org-left">+ - && ll ! ( ) { } [ ] ^ " ~ \* ? : /</td>
<td class="org-left">需要转义的字符</td>
</tr>


<tr>
<td class="org-left">(jakarta OR apache) AND website</td>
<td class="org-left">表达式 website存在并且有jakarta或者apache</td>
</tr>
</tbody>
</table>


<a id="org21fea94"></a>

### q.op

指定查询语句默认是用\*AND\*还是\*OR\*


<a id="org0e2e6e7"></a>

### df

指定默认搜索的字段


<a id="orgb42340f"></a>

## The DisMax Query Parser


<a id="org520f8fc"></a>

### Parameters


<a id="org705ea35"></a>

## Faceting

对结果进行分类(分组),很方便查询每个条件有多少文档。
必要条件：facet的字段必须被索引indexed=true


<a id="org837e39e"></a>

### General Parameters

1.  facet=true(on) ,  默认为假
    1.  不会改变结果字段，只会添加一个 facet\_counts 字段
2.  facet.query 指定计算count的表达式
    facet.query={!myfunc}name~fred


<a id="orgb7018b8"></a>

### Field-Value Faceting Parameters

1.  facet.field  
    分组的字段
2.  facet.prefix 
    限制facet.field 的前缀，不同则不分类
3.  facet.limit  
    facet\_counts 字段返回条数, 默认100
4.  facet.sort
    -   count 根据数量排序
    -   index (default)
5.  facet.offset 
    开始条数,偏移量,它与facet.limit配合使用可以达到分页的效果
6.  facet.mincount 
    facet\_counts 字段中最小的数量，低于此值不显示
7.  facet.missing 
    是否返回没有值的field
8.  facet.method 
    取值为enum或fc,默认为fc, fc表示Field Cache
    -   enum 适用于值较少的


<a id="org3ff07e9"></a>

### facet.pivot

不会翻译， 作用比较像是 mysql 中将两个字段进行分组,然后rollup,获得一个统计数据
返回字段 facet\_count.facet\_pivot

-   <http://localhost:8983/solr/techproducts/select?q=*:*&facet.pivot=cat,popularity,inStock&facet.pivot=popularity,cat&facet=true&facet.field=cat&facet.limit=5&rows=0&wt=json&indent=true&facet.pivot.mincount=2>


<a id="org0332cf5"></a>

## Highlighter


<a id="orgfe69e0b"></a>

### Standard Highlighter


<a id="org7d878b0"></a>

# solrCloud

server/solr


<a id="org513c7ad"></a>

## features

1.  集中式配置管理
2.  自动化负载均衡和故障切换
3.  ZooKeeper 整合


<a id="org8398698"></a>

## 相关概念


<a id="org98545f8"></a>

### Node

solr实例


<a id="org8e16ae2"></a>

### Cluster

可以包含多个Collection，由一个或者多个node组成


<a id="org5050b19"></a>

### Collection

在SolrCloud集群中逻辑意义上的完整的索引, 可以分到多个Shards上


<a id="org01425aa"></a>

### Config Set

Solr Core提供服务必须的一组配置文件


<a id="orgee662c0"></a>

### Leader

赢得选举的Shard replicas


<a id="org462c031"></a>

### Replica

Shard的一个拷贝


<a id="org6e59f6d"></a>

### Shard

Collection的逻辑分片。一个shard上面一个leader replica


<a id="org2fb1de6"></a>

### Zookeeper

Zookeeper提供分布式锁功能，对SolrCloud是必须的。它处理Leader选举。Solr可以以内嵌的Zookeeper运行，但是建议用独立的，并且最好有3个以上的主机。 


<a id="org365f153"></a>

## 配置外部 ZooKeeper

**需要多少Zookeeper** 想要挂掉F个机器时还能正常提供服务，就需要 2\*F+1 台机器
下载地址： <http://zookeeper.apache.org/releases.html>


<a id="orge445b25"></a>

### 一个实例

-   <ZOOKEEPER\_HOME>/conf/zoo.cfg

    # 一个滴答（时间单位， 毫秒）
    tickTime=2000 
    # 数据文件夹
    dataDir=/var/lib/zookeeper
    # 端口号
    clientPort=2181


<a id="org95ac737"></a>

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
    
    cd <ZOOKEEPER\_HOME>
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


<a id="orgc822580"></a>

### 通过zookeeper管理配置文件

上传配置文件
sh zkcli.sh -cmd upconfig -zkhost <host:port> -confname <name for configset> -solrhome <solrhome> -confdir <path to directory with configset>
cd *Users/wudanyang/self/solr/server/scripts/cloud-scripts
sh zkcli.sh -cmd upconfig -zkhost localhost:2181 -confname yang -confdir ..*../../server/solr/configsets/basic\_configs/conf


<a id="org2f76ba5"></a>

### 添加 node

-   zkServer.sh start \*.cfg
-   bin/solr start -cloud -s <conf path> -p 8987 -z localhost:2181 # 添加一个节点,配置文件夹中必须包含一个solr.xml文件
-   bin/solr start -cloud -s confs/cloud/conf/ -p 8984 -z localhost:2181,localhost:2182,localhost:2183
-   zkServer.sh stop


<a id="org6f3a646"></a>

### Collections API

创建多个shard需要多个node
nodeNum = shardNum \* replicationFactorNum

-   <http://localhost:8983/solr/admin/collections?action=CREATE&name=yang&numShards=1&replicationFactor=3&collection.configName=yang>
-   <http://localhost:8983/solr/admin/collections?action=RELOAD&name=yang_test2>


<a id="org8fb563c"></a>

## Run Examples


<a id="org3fe67d8"></a>

### 通过 bin/solr restart 可以重启节点

bin/solr restart -c -p 8983 -s example/cloud/node1/solr
-c 启动solrcloud模式
-p 指定端口
-h 指定host
bin/solr restart -c -p 7574 -z localhost:9983 -s example/cloud/node2/solr
-z zookeeper服务器地址


<a id="org712ee03"></a>

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


<a id="org8adf343"></a>

# Issues


<a id="org1b77193"></a>

## 学习时遇到的问题


<a id="org99efb79"></a>

### Q: ZooKeeper JMX enabled by default Using config: *Users/wudanyang/self/zoo/bin*../conf/zoo.cfg Error contacting service. It is probably not running.

A: bin/zkServer.sh start-foreground 可以查看到


<a id="orgd4e224d"></a>

### Q: ZooKeeper 执行 bin/zkServer.sh status 说未启动

A: ps aux | grep zookeeper
查看是否存在


<a id="org9762773"></a>

### Q: SolrCore Initialization Failures

A: 未上传配置
sh zkcli.sh -cmd upconfig -zkhost localhost:2181 -confname gettingstarted -confdir ../../../server/solr/configsets/basic\_configs/conf


<a id="org2ccda8d"></a>

### Q: 通过api创建collection时, 返回localhost未返回任何数据

A: 请求地址应该是solr服务器，而不是zookeeper服务器。
localhost:8983/solr/admin/collectinos?action=CREATE&name=yang&numShards=1&replicationFactor=3&collection.configName=yang


<a id="org3d0f69e"></a>

### Q: Cannot create collection tinycollection. Value of maxShardsPerNode is 1, and the number of live nodes is 4. This allows a maximum of 4 to be created. Value of numShards is 2 and value of replicationFactor is 3. This requires 6 shards to be created (higher than the allowed number)</str>

A:将replicationFactor降低
<http://localhost:8983/solr/admin/collections?action=CREATE&name=yang&collection.configName=yang&numShards=1&replicationFactor=1&wt=json>


<a id="org9c87174"></a>

### Q: 在zookeeper中找不到配置文件

A: 配置文件疑似在上传到zookeeper时放到了名为zoo\_data/version-{num}/log.number的二进制文件中


<a id="org008e8be"></a>

### Q: 为何在6.\*以上的solr中store=false 仍然能看到字段被返回了

A: 在6.\*之后，string 的 docValues=true 为默认值


<a id="org154c8db"></a>

### Q: int类型为何docValues=false与stored=false还能在结果中看到字段

A: 未知


<a id="org14d1849"></a>

### Q: 从 example/example-DIH/solr/ 中复制solr.xml 作为cloud的配置文件无法生效

A: 因为默认的配置文件里面有 standalone="yes" 及不使用集群方式


<a id="org055d119"></a>

### Q: 为什么找不到 Can't find resource 'schema.xml'

A: example 文件夹中的配置文件为 managed-schema 需要改成 schema.xml 上传才行


<a id="orgf629ff2"></a>

## 公司系统发现的问题

1.  脚本文件处于无版本控制状态
    创建git本地库，后续可以跟运维商量加上一个solr脚本的git库


<a id="org231e13f"></a>

# Cache

缓存在 Solr 中充当了一个非常重要的角色，Solr 中主要有这三种缓存：

1.  Filter cache（过滤器缓存），用于保存过滤器（fq 参数）和层面搜索的结果
2.  Document cache（文档缓存），用于保存 lucene 文档存储的字段
3.  Query result（查询缓存），用于保存查询的结果
4.  还有第四种缓存，lucene 内部的缓存，不过该缓存外部无法控制到。

通过这 3 种缓存，可以对 solr 的搜索实例进行调优。调整这些缓存，需要根据索引库中文档的数量，每次查询结果的条数等。
在调整参数前，需要事先得到 solr 示例中的以下信息： 索引中文档的数量 每秒钟搜索的次数 过滤器的数量 一次查询返回最大的文档数量
不同查询和不同排序的个数，这些数量可以在 solr admin 页面的日志模块找到。

假设以上的值分别为：
索引中文档的数量：1000000
每秒钟搜索的次数：100
过滤器的数量：200
一次查询返回最大的文档数量：100
不同查询和不同排序的个数：500
然后可以开始修改 solrconfig.xml 中缓存的配置了，

第一个是过滤器缓存：
第二个是查询结果缓存：
第三个是文档缓存：
这几个配置是基于以上的几个假设的值进行调优的。


# Footnotes

<sup><a id="fn.1" href="#fnr.1">1</a></sup> 正排索引是指由文档找词，倒排索引是指由词找文档
