## Elasticsearch

目录

- Elasticsearch是什么
- CentOS下安装与运行



####  Elasticsearch是什么

Elasticsearch 是一个分布式、RESTful 风格的搜索和数据分析引擎，能够解决不断涌现出的各种用例。作为 Elastic Stack 的核心，它集中存储您的数据，帮助您发现意料之中以及意料之外的情况。

- 基于lucene

- 通过 Elasticsearch，能够执行及合并多种类型的搜索（结构化数据、非结构化数据、地理位置、指标），搜索方式随心而变
- 搜索速度快
- 可扩展性——它能够水平扩展，每秒钟可处理海量事件，同时能够自动管理索引和查询在集群中的分布方式
- 弹性  Elasticsearch 运行在一个分布式的环境中,可利用集群弹性伸缩



---

#### CentOS下安装与运行

- 前提条件 

      -  需要先配置JDK环境,如果已经安装openjdk的建议删了装Oracle的
      -  只能运行在非root用户下

- 下载  `wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.1.1-linux-x86_64.tar.gz`

- 解压 `tar -zxvf  elasticsearch-7.1.1-linux-x86_64.tar.gz`

- 简单修改下配置  `vim  config/elasticsearch.yml` 将**#http.port: 9200**的#去掉

- 运行  

  ``` cd bin  ``` 

  `/elasticsearch -d` 

用`curl http://localhost:9200/`如果出现下面结果则正常启动

```
[levy@localhost bin]$ curl http://localhost:9200/
{
  "name" : "localhost.localdomain",
  "cluster_name" : "elasticsearch",
  "cluster_uuid" : "qeqxlZQgTEGSXPfL5nDHmg",
  "version" : {
    "number" : "7.1.1",
    "build_flavor" : "default",
    "build_type" : "tar",
    "build_hash" : "7a013de",
    "build_date" : "2019-05-23T14:04:00.380842Z",
    "build_snapshot" : false,
    "lucene_version" : "8.0.0",
    "minimum_wire_compatibility_version" : "6.8.0",
    "minimum_index_compatibility_version" : "6.0.0-beta1"
  },
  "tagline" : "You Know, for Search"
}

```

