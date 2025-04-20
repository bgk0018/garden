---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/data-windowing-in-kafka-streams-202501251120/","tags":["♣️/kafka","📖"],"created":"2025-02-24T16:13:19.425-06:00","updated":"2025-02-02T15:54:17.840-06:00"}
---


# Content

There are 4 types of windowing in Kafka Streams:
- Hopping
- Tumbling
- Sliding
- Session

Hopping windows are a fixed time period of data given a specific advancing time. For example, we could define a hopping window as a 5 minute period every 1 minute. This means that hopping windows overlap. This is triggered by size and period.

Tumbling windows are a special type of hopping window where the fixed time period of data is equal to the advance period, meaning that unlike hopping windows, the primary property of a tumbling window is that it's periods do not overlap. This is triggered by size and period.

Sliding windows are time-based windows that are evaluated based on the current event's timestamp. Unlike hopping or tumbling windows which have fixed boundaries, sliding windows create a new window for each event, centered around that event's timestamp. The window includes all events that occurred within a specified time range before and after the current event. This is triggered by each event and the window size.

Sessions windows define a time period in which the window will expire if a new event isn't detected. As long as a new event is added within the expiration period, then the window will continue to grow. This is triggered by an event. The time period that determines expiration is called the 'Inactivity Gap'.

All windows also have a grace period component where if an event arrives that comes in out of order and should be included in a specific window, can still be included in the aggregation.

# References

[[projects/Dallas Confluent Practice/Windowing in Kafka Streams\|Windowing in Kafka Streams]]

# Flashcards

What are the four types of windowing in Kafka Streams?:: Hopping, Tumbling, Sliding, and Session windows.
<!--SR:!2025-01-29,3,250-->

What is a hopping window in Kafka Streams and what triggers it?:: A fixed time period of data with a specific advancing time that creates overlapping windows. For example, a 5-minute window every 1 minute. It is triggered by size and period.
<!--SR:!2025-01-29,3,250-->

What is a tumbling window and how does it differ from a hopping window?:: A tumbling window is a special type of hopping window where the fixed time period equals the advance period, meaning windows don't overlap. It is triggered by size and period.
<!--SR:!2025-01-29,3,250-->

What is a sliding window and how is it unique?:: A time-based window evaluated on each event's timestamp, creating a new window centered around each event. It includes events within a specified time range before and after the current event. It is triggered by each event and window size.
<!--SR:!2025-01-29,3,250-->

What is a session window and what is the 'Inactivity Gap'?:: A window that grows as long as new events arrive within the expiration period. The 'Inactivity Gap' is the time period that determines when the window expires if no new events are detected. It is triggered by events.
<!--SR:!2025-01-29,3,250-->

What is the grace period in Kafka Streams windowing?:: A time period that allows out-of-order events to still be included in their appropriate window's aggregation.
<!--SR:!2025-01-29,3,250-->
