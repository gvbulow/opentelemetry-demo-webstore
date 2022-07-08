# Integration with Elasticsearch APM

This document describes the modifications made for sending OpenTelemetry traces, metrics and logs to Elasticsearch APM

## Pre-requisites

- Docker Desktopp
- Elastic Agent 8.x with APM integration installed locally

Check connection to APM with `curl http://localhost:8200`. Expected result:

```
{
  "build_date": "2022-05-25T06:13:22Z",
  "build_sha": "5bd955fad9c4e20c0fa404d3a7f34ae1973803fe",
  "publish_ready": true,
  "version": "8.2.2"
}
```

## Running with OpenTelemety Collector

The basic configuration just adds an OTLP Exporter pointing to APM to the OpenTelemetry Collector. After running `docker compose up -d` data will start flowing into APM. The APM Service Map will look like this:

[![Elasticsearch APM Service Map](../img/apm-service-map.png)](../img/apm-service-map.png)

## Connecting OpenTelemetry Agents directly to APM