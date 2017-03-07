<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#org55fa3ce">1. 前言</a></li>
<li><a href="#org16417d6">2. 环境需求</a></li>
<li><a href="#org5a9ac0d">3. 安装步骤</a></li>
<li><a href="#org29c5090">4. 简单运行</a></li>
<li><a href="#orgc181dce">5. Core Or Collection</a></li>
<li><a href="#org8af4c70">6. 向solr中添加文档</a></li>
<li><a href="#org2db6989">7. 请求数据</a></li>
</ul>
</div>
</div>

<a id="org55fa3ce"></a>

# 前言

最近在研究 solr ，从头开始学习。
solr 的文档大概扫了一遍，其中重要的和能在工作中用到的都记了下来。
这几天整理一下记录的笔记。

solr 主要用来构建搜索服务，向 solr 中填入数据，然后从其中取数据。
相当于一个数据库的角色。


<a id="org16417d6"></a>

# 环境需求

-   JRE version >= 1.8


<a id="org5a9ac0d"></a>

# 安装步骤

1.  下载solr包
    -   地址 <http://lucene.apache.org/solr/>
2.  解压
    -   tar zxf solr-x.y.z.tgz


<a id="org29c5090"></a>

# 简单运行

    bin/solr start
    
    bin/solr -help
    # 指定命令的帮助文档
    bin/solr start -help
    
    # 前端开启Foreground
    bin/solr start -f
    # 指定端口 (默认是8983)
    bin/solr start -p 8984
    bin/solr stop [-p 8983 | -all]
    
    # 启动示例 solr 实例
    bin/solr -e techproducts [techproducts, dih, schemaless, and cloud.]
    
    # 查看运行状态
    bin/solr status


<a id="orgc181dce"></a>

# Core Or Collection

-   Core 是以单实例模式启动的 solr
-   每个core有自身的配置文件及数据
    
        bin/solr create -c <name>
        bin/solr create -help


<a id="org8af4c70"></a>

# 向solr中添加文档

schema 决定了文档的结构
solr bin/post -help


<a id="org2db6989"></a>

# 请求数据

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

