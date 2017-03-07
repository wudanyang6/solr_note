<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#orgb8e51ba">1. 前言</a></li>
<li><a href="#org6f0fd44">2. 访问</a></li>
<li><a href="#orgde2a4ed">3. 获取帮助</a></li>
<li><a href="#orgd6fac92">4. Logging</a></li>
<li><a href="#org18dfa23">5. Cloud (仅在 Cloud 模式下显示)</a>
<ul>
<li><a href="#orge0e64e4">5.1. Tree</a></li>
<li><a href="#org4348a81">5.2. graph</a></li>
<li><a href="#org46fbb60">5.3. Dump</a></li>
</ul>
</li>
<li><a href="#org77dd2ad">6. Core Admin</a></li>
<li><a href="#orgcdaeda7">7. Thread Dump</a></li>
<li><a href="#org4cba003">8. Collection-Specific Tools(只有在cloud下才能看到)</a>
<ul>
<li><a href="#org8487f71">8.1. Analysis</a></li>
<li><a href="#org56b540f">8.2. Documents</a></li>
<li><a href="#orgecdd3a9">8.3. Files</a></li>
<li><a href="#org528b590">8.4. Query</a></li>
<li><a href="#orgabd4c59">8.5. Stream</a></li>
<li><a href="#orga04a83b">8.6. Schema</a></li>
</ul>
</li>
</ul>
</div>
</div>

<a id="orgb8e51ba"></a>

# 前言

通过 solr 提供的用户界面,
可以很方便地管理 solr 并且能提高开发效率。


<a id="org6f0fd44"></a>

# 访问

<http://hostname:port/solr>

默认是<http://localhost:8983>


<a id="orgde2a4ed"></a>

# 获取帮助

底部链接

-   帮助文档
-   issue tracker
-   IRC 聊天室
-   社区论坛
-   查询语句的语法


<a id="orgd6fac92"></a>

# Logging

-   黄色高亮的有记录日志的能力
-   黑体字部分不受root影响


<a id="org18dfa23"></a>

# Cloud (仅在 Cloud 模式下显示)


<a id="orge0e64e4"></a>

## Tree

显示zookeeper内部数据


<a id="org4348a81"></a>

## graph

显示collection的分片信息


<a id="org46fbb60"></a>

## Dump

获取一份ZooKeeper中的solr数据快照。（帮助调试）


<a id="org77dd2ad"></a>

# Core Admin

管理 Core 


<a id="orgcdaeda7"></a>

# Thread Dump

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
<td class="org-left">TIMED<sub>WAITING</sub></td>
<td class="org-left">有时间的等待</td>
</tr>


<tr>
<td class="org-left">TERMINATED</td>
<td class="org-left">退出</td>
</tr>
</tbody>
</table>


<a id="org4cba003"></a>

# Collection-Specific Tools(只有在cloud下才能看到)


<a id="org8487f71"></a>

## Analysis

分析查询语句,使用 solr 内置分词时能够便于调试


<a id="org56b540f"></a>

## Documents

更新数据


<a id="orgecdd3a9"></a>

## Files

configuration files | solrCloud 展示的是 ZooKeeper 中的配置文件

1.  solrconfig.xml
    -   定义了 solr 如何索引内容和响应请求
2.  Schema 定义数据类型
    -   文档字段


<a id="org528b590"></a>

## Query

在 query 界面可以很方便的查询 solr 中的数据


<a id="orgabd4c59"></a>

## Stream

raw版本的query界面


<a id="orga04a83b"></a>

## Schema

1.  选择字段-可以查看在 schema 中定义的字段的属性
2.  load term info 加载示例数据

