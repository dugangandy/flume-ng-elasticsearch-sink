## 本项目基于开源项目https://github.com/lucidfrontier45/ElasticsearchSink2 开发. 您也可以使用Logstash来替代flume。

# flume-ng-elasticsearch-sink

This is Flume-NG Sink for Elasticsearch >= 6.5.4.
I developed this because the official version does not support Elasticsearch >= 6.5.4 due to API changes.


# Requirements

- Flume-NG >= 1.7
- Elasticsearch >= 6.5.4

# Build

Build standard jar by the following command

```bash
$ ./gradlew build
```

Build fat jar which contains elasticsearch dependencies
```bash
$ ./gradlew assembly
```

Jar will be generated in `build/libs`（推荐使用该方式）


# Usage

1. 将编译后的jar包放到flume的默认lib目录下，替换掉默认的flume-ng-elasticsearch-sink-1.7.0.jar.
2. 从flume默认lib目录下删除 `guava-*.jar` and `jackson-core-*.jar` and `lucene-*.jar`. 这些包的版本已经过时，新版本已经包含在编译的jar包中.
3. 修改 flume.conf 的elasticsearch sink类名.（采用本项目代码编译，无需修改）
4. 启动flume agent.
