# Elasticsearch概念

官网： [Elasticsearch：官方分布式搜索和分析引擎](https://www.elastic.co/cn/elasticsearch/)



## 关键词

* 2010年发布
* 基于Lucene
* 实时，添加的文档在一秒钟后就可以在引擎中搜索得到
* 分布式，易于在任何大型组织中扩展和集成
* 开源
* 全文搜索和分析
* RESTful Web（默认9200端口）
* java开发跨平台，它在几乎每个平台上都兼容.
* 存储JSON对象，这使得可以使用不同的编程语言调用Elasticsearch服务器.
* 分片和复制，从而方便水平分割和扩展，复制保证了es的高可用与高吞吐。

* 可扩展高达PB级的结构化和非结构化的数据。
* 可文档存储，替代MongoDB和RavenDB。
* 使用非标准化来提高性能。

## 概念

| 概念      | 解释                                                         |
| --------- | ------------------------------------------------------------ |
| 节点      | Elasticsearch正在运行的单个实例，一个物理机或虚拟机可容纳多个几点。 |
| 集群      | 一个或多个节点的集合，为整个系统提供跨所有节点的索引和搜索功能。 |
| 索引      | 不同类型的文档和属性的集合，使用分片的概念来提高性能。       |
| 类型/映射 |                                                              |
| 文档      | 以json格式定义的字段集合，每个文档都有索引，每个文档有唯一标识符（UID）。 |
| 碎片      | 索引被水平细分为碎片。每个碎片包含文档的所有属性，但包含的数量比文档少，水平分割使碎片成为一个独立的节点，可以存储在任何节点中。<br />主碎片是索引的原始水平部分，然后这些主碎片被复制到副本碎片中。 |
| 副本      | Elasticsearch允许创建索引和分片的副本。<br />不仅有利于在故障情况下增加数据可用性，而且还通过在这些副本中执行并行搜索操作来提高搜索性能。 |



## 比较

Elasticsearch和关系型数据库的比较：

| Elasticsearch                                      | 关系型数据库     |
| -------------------------------------------------- | ---------------- |
| Index                                              | Database         |
| Type                                               | Table            |
| Document                                           | Row              |
| Field                                              | Column           |
| Mapping                                            | Schema           |
| 倒排索引（inverted index）<br />所有域默认加了索引 | B-Tree索引、、、 |



## 缺点

* 没有典型意义上的事务
* 没有授权和认证



# 环境安装

## 环境：

* CentOS Linux release 7.9.2009 (Core)
* java 1.8.0_291

## 下载地址

[Download Elasticsearch](https://www.elastic.co/cn/downloads/elasticsearch)

* 对于Windows操作系统，请下载ZIP文件。

* 对于UNIX操作系统，请下载TAR文件。

* **对于Debian操作系统，请下载DEB文件。**

* 对于Red Hat和其他Linux发行版，请下载RPM文件。

* APT和Yum实用程序也可用于在许多Linux发行版中用来安装Elasticsearch。

这里我们下载最新的rpm版本：https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.15.2-x86_64.rpm

## 安装

```shell
#1.下载
curl -o elasticsearch-7.15.2-x86_64.rpm https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.15.2-x86_64.rpm
#或 wget -O elasticsearch-7.15.2-x86_64.rpm https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.15.2-x86_64.rpm

#2.安装
yum install elasticsearch-7.15.2-x86_64.rpm
#默认安装到了/etc/elasticsearch     /usr/share/elasticsearch
	
#3.一系列设置
#因为elasticsearch自动创建的用户elasticsearch是默认无法登录的，所以这里先把用户elasticsearch的shell更改为/bin/bash
usermod elasticsearch -s /bin/bash
usermod -a -G root elasticsearch
#授予这个目录权限，不然会报错：
chmod -R 777 /var/log/elasticsearch
#然后用elasticsearch用户登录：
su elasticsearch
/usr/share/elasticsearch/bin/elasticsearch  #启动
```

#启动之后访问localhost:9200来测试：

```shell
curl localhost:9200
```

正常情况下会返回类似结果：

{
  "name" : "bogon",
  "cluster_name" : "elasticsearch",
  "cluster_uuid" : "PCT7fmNcTm2Zkkd0AkWhcg",
  "version" : {
    "number" : "7.15.2",
    "build_flavor" : "default",
    "build_type" : "rpm",
    "build_hash" : "93d5a7f6192e8a1a12e154a2b81bf6fa7309da0c",
    "build_date" : "2021-11-04T14:04:42.515624022Z",
    "build_snapshot" : false,
    "lucene_version" : "8.9.0",
    "minimum_wire_compatibility_version" : "6.8.0",
    "minimum_index_compatibility_version" : "6.0.0-beta1"
  },
  "tagline" : "You Know, for Search"
}



# 入门

## PostMan与Elasticsearch









## 创建索引







## 更新索引







## 获取索引







## 删除文档









## 搜索





。。。

