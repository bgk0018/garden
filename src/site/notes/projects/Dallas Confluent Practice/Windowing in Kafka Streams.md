---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/windowing-in-kafka-streams/","title":"Windowing in Kafka Streams","tags":["📰"],"created":"2025-02-22T11:20:09.362-06:00","updated":"2025-01-26T11:40:54.000-06:00"}
---


# Windowing in Kafka Streams

## Concepts

| Name                                                                                                                            | Weight    |
| ------------------------------------------------------------------------------------------------------------------------------- | --------- |
| [[projects/Dallas Confluent Practice/Notes/Data Windowing in Kafka Streams - 202501251120\|Data Windowing in Kafka Streams]] | Weight: 0 |

{ .block-language-dataview}

>[!summary]- Description

## Content

## What Is Windowing?

If you’re creating an application with Kafka Streams or ksqlDB, and that application involves aggregations, it’s likely that you’ll use windowing. 

Why is that?

Well, aggregations of data accumulate over time, and without a limit, these aggregations won’t *stop* accumulating. Enter windowing, which defines the amount of data that can accumulate. 

Note that windowing takes four forms, depending on whether the window is defined by size and period, or whether the window is event-triggered.

| **Size and Period** | **Event-Triggered** |
| --- | --- |
| Hopping | Session |
| Tumbling | Sliding |

For example, say that you’re designing an [application using moisture sensors](https://www.confluent.io/ko-kr/blog/using-data-pipelines-for-real-time-alerting-with-ksqldb/) to alert when a houseplant gets too dry. You can perform a filter for plants with low moisture readings in the past hour. If that filter returns anything, that event can trigger an aggregation over a window tumbling on every hour. The result is written to the alerts. 

Let’s take a look at each of the types of windowing in finer detail. 

## Hopping

### What is a Hopping Window?

![hopping-window](https://images.ctfassets.net/8vofjvai1hpv/4gXt3w1ZjWUVlFSUPxEx9p/5ddb49c62a5a67b66d16a82b820238ac/hopping-window.png)

A hopping window is bound by time and defined by a window size and the size of the time block at which it advances (both measured in seconds).

Consider the red window in the above diagram and think about it advancing through time: if you had a window size of 50 seconds but an advance size of 15 seconds, there would be an overlap of 35 seconds between the windows. In a hopping window, the window size is usually set to a larger amount of time than the advance size. The above diagram shows what an overlap might look like if you took the window as a rectangle and superimposed it over a wavy stream of data—the rectangles that overlap represent the overlapping window.

Note: Tumbling windows never overlap or have gaps. Hopping windows might have gaps or overlaps, or they might not. 

A classic example of a hopping window implementation is a dashboard with moving averages—say, average clicks on a certain e-commerce page, like a product details page for an air fryer, for 2-minute windows in the past 24 hours. 

### Creating a Hopping Window

As stated above, there are two key pieces of information you need to configure hopping windows: window size and advance size. 

When you’re working with Kafka Streams, you need to set both a `windowSize` and `advanceSize`. See the more complete example in this [Kafka Streams 101](https://developer.confluent.io/learn-kafka/kafka-streams/windowing/) tutorial. 

If you’re implementing a hopping window with ksqlDB, then you need to make sure to create a table using the `WINDOW HOPPING` syntax. You’ll set the two sizes with `SIZE` and `ADVANCE BY`. You can view a more complete example in this [tutorial](https://developer.confluent.io/tutorials/create-hopping-windows/ksql.html). 

## Tumbling

### What is a Tumbling Window?

![tumbling-window](https://images.ctfassets.net/8vofjvai1hpv/3TDxKKEPrfPexT9prlzPJX/4024826906191c48969d1311aefebac3/tumbling-window.png)

Similar to hopping windows, tumbling windows are also time-based. In fact, a tumbling window is a special subtype of hopping window where `windowSize` and `advanceSize` are the same. This means an individual event will only ever be present in one tumbling window––no duplicates. As you can see, this diagram differs from the former in that the rectangles do not overlap, representing the non-overlapping windows. 

Tumbling windows are useful for reporting where you want events to belong to a single window, like taking the aggregate of credit card swipes in the last 55 seconds. 

### Creating a Tumbling Window

Creating a tumbling window in Kafka Streams uses the same process as a hopping window, but you need to make sure that `windowSize` and `advanceSize` are the same. 

In ksqlDB, you use the `WINDOW TUMBLING` syntax on a `TABLE` and set the `SIZE`. The tutorials section on the Confluent website houses a full example: [How to create tumbling windows](https://developer.confluent.io/tutorials/create-tumbling-windows/ksql.html).

## Session

### What is a Session Window?

![session-window](https://images.ctfassets.net/8vofjvai1hpv/24AcJMi6KMC7Pmrew1ardu/1717ae0d7f6ed95c0d675d10566aa636/session-window.png)

A session window is triggered by events. The mechanism involves something called an “inactivity gap.” This gap is the amount of time within which the window will grow *unless interrupted by a new event*. When a new event flows in as input, the inactivity window resets and the window continues to grow. If your inactivity window is too short or you have lots of events, this can result in a very long window! 

In the above diagram, the inactivity gaps are represented by blue rectangles, separated by an event which is represented by a star. The rectangle representing the session window spans the inactivity gaps. 

Use cases involve tracking user activity if you wanted to know how many events were generated over a period of time (e.g., how long *exactly* was the user’s FlixMovie binge?). 

### Creating a Session Window

Creating a session window in Kafka Streams involves setting an `inactivityGap`. You can see a more complete description in this tutorial: [Windowing](https://developer.confluent.io/learn-kafka/kafka-streams/windowing/). 

The other option is to use ksqlDB, employing a table with a `WINDOW SESSION` syntax. You can view a tutorial on this here: [Create session windows](https://developer.confluent.io/tutorials/create-session-windows/ksql.html). 

## Sliding

### What is a Sliding Window?

![sliding-window](https://images.ctfassets.net/8vofjvai1hpv/36SJwa8C0qIfB8tGW6FXH5/874abf47a4bd381315c9a2efc3bc4b55/sliding-window.png)

A sliding window is also time-based, so the size of the window is defined in seconds. In order for a sliding window to be triggered, some user events must happen within a defined window of time. For example, you might use this type of window if you wanted to calculate the data between “add-to-cart” and “purchase” events from users that were made within the defined amount of time of three hours. 

In the diagram above, the defined amount of time is represented by a large light-blue rectangle. The user events are represented by two gold stars, and the purple rectangle between them represents the data window. 

### Creating a Sliding Window

When you create a sliding window in the Streams API, you need to set `timeDifference`. You can find a more complete example in this [windowing tutorial on Confluent Developer](https://developer.confluent.io/learn-kafka/kafka-streams/windowing/). 

Support for explicitly setting sliding windows is not yet available in ksqlDB. 

## A Note on Late Events

What if your events arrive late? It could skew your analysis; therefore, you can introduce “grace periods” in tumbling, hopping, and sliding windows. It’s basically a set amount of time in which events will be caught by the window, even though the time stamps of those events are greater than the window’s end. Note that events that occur after the grace period won’t be included—those are late for good and will be missed. Session windows don’t have grace periods because they are based on user behavior only, rather than time. 

Since [KIP-633](https://cwiki.apache.org/confluence/display/KAFKA/KIP-633%3A+Deprecate+24-hour+Default+Grace+Period+for+Windowed+Operations+in+Streams), there is no default grace period for Kafka Streams. However, [in ksqlDB](https://docs.ksqldb.io/en/latest/concepts/time-and-windows-in-ksqldb-queries/#:~:text=The%20default%20grace%20period%20is%2024%20hours.&text=Tune%20the%20update%20frequency%20by,streams.), the default is 24 hours. 

## Where to Go From Here

If you found this introduction to windowing with Apache Kafka® useful, you may also be interested in this list of resources for a deeper dive:

- A Kafka Stream video from the Kafka Streams 101 course: [Windowing](https://developer.confluent.io/learn-kafka/kafka-streams/windowing/)
- [Kafka Streams Application](https://developer.confluent.io/tutorials/creating-first-apache-kafka-streams-application/confluent.html) tutorial
- [ksqlDB 101 course](https://developer.confluent.io/learn-kafka/ksqldb/intro/?utm_medium=sem&utm_source=google&utm_campaign=ch.sem_br.nonbrand_tp.prs_tgt.dsa_mt.dsa_rgn.namer_lng.eng_dv.all_con.online-talks&utm_term=&placement=&device=c&creative=&gclid=CjwKCAiApvebBhAvEiwAe7mHSLEpVOhNBVyjLRmvSW1syRU2PV13j906tmyRipYvI8xphKx6tUxn5xoCTm0QAvD_BwE)
- [Streams tutorials list](https://developer.confluent.io/tutorials/)
- See the [Event Aggregator pattern](https://developer.confluent.io/patterns/stream-processing/event-aggregator/)
