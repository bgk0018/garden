---
{"dg-publish":true,"permalink":"/projects/southwest-airlines-sales/sales-meeting-meeting-202409231530/","tags":["👥","📫"],"created":"2024-09-23T15:29:59.320-05:00","updated":"2024-11-10T17:24:46.745-06:00"}
---


# Sales Meeting Meeting - 202409231530

---

## Goals / Agenda

1. Talking about Flink and Confluent/Kafka for Southwest

## Discussion Notes

- Neelima relatively new in data, history in application development
- Know that we've done data streaming with other airlines and looking for a partner
- Have teams looking on unifying different data sets and enabling our initiatives for workforce data, pilot data etc and leverage AI for downstream system decision making
- Working closely with AI team for scaling
- Challenges:
	- How to enable real-time streaming analytics
		- Medallion architecture
		- When lands in kafka, it also lands in lake
		- Pushed down to warehouse
	- What tools should we use? Watching what tools are available
- [[Nick Larson\|Nick Larson]]: Done this across many other clients, Thrivent
	- Were able to leverage for realtime efforts
		- Flink
	- Data liberation
- [[Neelima\|Neelima]] all of our systems are configured to listen to kafka and react to data that comes through
	- User interface are in a good position
	- We are struggling to make this data available for downstream people and dashboard building
- Move from 30 minutes today to something much more quickly
	- Looking at managed Flink in AWS
- Latency for the warehouse
- Made a lot strides in data governance, highly integrated once data lands not when data is in motion
- Using avro schema, don't carry the history of the record

## Action Items

## Related

| Meetings                                                                                                            | Date                                          |
| ------------------------------------------------------------------------------------------------------------------- | --------------------------------------------- |
| [[projects/Southwest Airlines Sales/Sales Meeting Meeting - 202409231530\|Sales Meeting Meeting - 202409231530]] | [[journal/1-daily/2024-09-23\|2024-09-23]] |

{ .block-language-dataview}
