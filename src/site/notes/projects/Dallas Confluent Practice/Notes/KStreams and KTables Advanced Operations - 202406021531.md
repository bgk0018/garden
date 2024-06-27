---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/k-streams-and-k-tables-advanced-operations-202406021531/","tags":["📖","♣️/kafka"],"created":"2024-06-03T14:22:23.513+01:00","updated":"2024-06-03T14:32:00.176+01:00"}
---

# KStreams and KTables Advanced Operations

## KTable groupBy

- GroupBy allows you to preform more aggregations within a KTable

> [!WARNING]  
> Go look this up, very brief

## KGroupedStream / KGroupedTable Count

- Counts the number of record by grouped key
- KGroupedStream: Null keys and values are ignored
- KGroupedTable: Null keys are ignored, null values are treated as 'delete' = tombstones

## KGroupedStream Aggregate

- You need an initializer of any type, an adder, a Serde and a State Store name (name of your aggregation)
- When using with a Stream, you need an adder
- When using with a Table, you need an adder and subtractor (what happens when data is deleted)

## KGroupedStream/Table Reduce

- Similar to Aggregate, but the result type has to be the same as an input

## KStream Peek

- Peek allows you to apply a side-effect operation to a KStream and get the same KStream as a result
- Effectively Tee
- This is an at least once operation

## KStream Transform/TransformValues

- applies a transformer to each record
- Very low level

# References


# Flashcards