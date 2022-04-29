## 9.1.0

#### Project

* Upgrade zipkin to 2.23.16.

#### OAP Server

* Add component definition(ID=127) for `Apache ShenYu (incubating)`.
* Fix Zipkin receiver: Decode spans error, missing `Layer` for V9 and wrong time bucket for generate Service and
  Endpoint.
* [Refactor] Move SQLDatabase(H2/MySQL/PostgreSQL), ElasticSearch and BanyanDB specific configurations out of column.
* Support BanyanDB global index for entities. Log and Segment record entities declare this new feature.
* Remove unnecessary analyzer settings in columns of templates. Many were added due to analyzer's default value.
* Simplify the Kafka Fetch configuration in cluster mode.
* [Breaking Change] Update the eBPF Profiling task to the service level, please delete
  index/table: `ebpf_profiling_task`, `process_traffic`.
* Fix event can't split service ID into 2 parts.
* Fix OAP Self-Observability metric `GC Time` calculation.
* Set `SW_QUERY_MAX_QUERY_COMPLEXITY` default value to `1000`
* Webapp module (for UI) enabled compression.
* [Breaking Change] Add layer field to event, report an event without layer is not allowed.
* Fix ES flush thread stops when flush schedule task throws exception, such as ElasticSearch flush failed.
* Fix ES BulkProcessor in BatchProcessEsDAO was initialized multiple times and created multiple ES flush schedule tasks.
* HTTPServer support the handler register with allowed HTTP methods.
* [Critical] Revert [**Enhance DataCarrier#MultipleChannelsConsumer to add
  priority**](https://github.com/apache/skywalking/pull/8664) to avoid consuming issues.
* Fix the problem that some configurations (such as group.id) did not take effect due to the override order when using the kafkaConsumerConfig property to extend the configuration in Kafka Fetcher.
* Remove build time from the OAP version.
* Add data-generator module to run OAP in testing mode, generating mock data for testing.
* Support receive Kubernetes processes from gRPC protocol.
* Fix the problem that es index(TimeSeriesTable, eg. endpoint_traffic, alarm_record) didn't create even after rerun with init-mode. This problem caused the OAP server to fail to start when the OAP server was down for more than a day.
* Support autocomplete tags in traces query.
* [Breaking Change] Replace all configurations `**_JETTY_**` to `**_REST_**`.
* Clean up scroll contexts after used.

#### UI

* General service instance: move `Thread Pool` from JVM to Overview, fix `JVM GC Count` calculation.
* Add Apache ShenYu (incubating) component LOGO.
* Show more metrics on service/instance/endpoint list on the dashboards.
* Support average values of metrics on the service/list/endpoint table widgets, with pop-up linear graph.
* Fix viewLogs button query no data.
* Fix UTC when page loads.
* Implement the eBPF profile widget on dashboard.

#### Documentation

All issues and pull requests are [here](https://github.com/apache/skywalking/milestone/128?closed=1)
