---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/schema-evolution-compatibility-matrix-202404101240/","tags":["♣️/kafka","📖"],"created":"2025-05-12T23:14:29.080-05:00","updated":"2025-01-26T11:40:34.575-06:00"}
---


# Schema Evolution Compatibility Matrix

| Compatibility Type    | Changes allowed                                   | Check against which schemas     | Upgrade first |
| --------------------- | ------------------------------------------------- | ------------------------------- | ------------- |
| `BACKWARD`            | - Delete fields<br>- Add optional fields          | Last version                    | Consumers     |
| `BACKWARD_TRANSITIVE` | - Delete fields<br>- Add optional fields          | All previous versions           | Consumers     |
| `FORWARD`             | - Add fields<br>- Delete optional fields          | Last version                    | Producers     |
| `FORWARD_TRANSITIVE`  | - Add fields<br>- Delete optional fields          | All previous versions           | Producers     |
| `FULL`                | - Add optional fields<br>- Delete optional fields | Last version                    | Any order     |
| `FULL_TRANSITIVE`     | - Add optional fields<br>- Delete optional fields | All previous versions           | Any order     |
| `NONE`                | - All changes are accepted                        | Compatibility checking disabled | Depends       |

## Flashcards

What changes are allowed in BACKWARD compatibility and what needs to be upgraded first?:: BACKWARD allows deleting fields and adding optional fields. Consumers must be upgraded first.
<!--SR:!2025-01-28,3,250-->

What changes are allowed in BACKWARD_TRANSITIVE compatibility and how does it differ from BACKWARD?:: BACKWARD_TRANSITIVE allows deleting fields and adding optional fields, but checks against all previous versions instead of just the last version. Consumers must be upgraded first.
<!--SR:!2025-01-29,3,250-->

What changes are allowed in FORWARD compatibility and what needs to be upgraded first?:: FORWARD allows adding fields and deleting optional fields. Producers must be upgraded first.
<!--SR:!2025-01-29,3,250-->

What changes are allowed in FORWARD_TRANSITIVE compatibility and how does it differ from FORWARD?:: FORWARD_TRANSITIVE allows adding fields and deleting optional fields, but checks against all previous versions instead of just the last version. Producers must be upgraded first.
<!--SR:!2025-01-28,3,250-->

What changes are allowed in FULL compatibility and what's unique about its upgrade order?:: FULL allows adding optional fields and deleting optional fields. Components can be upgraded in any order.
<!--SR:!2025-01-29,3,250-->

What changes are allowed in FULL_TRANSITIVE compatibility and how does it differ from FULL?:: FULL_TRANSITIVE allows adding optional fields and deleting optional fields, but checks against all previous versions instead of just the last version. Components can be upgraded in any order.
<!--SR:!2025-01-28,3,250-->

What is special about NONE compatibility?:: NONE accepts all changes and disables compatibility checking. The upgrade order depends on the specific changes made.
<!--SR:!2025-01-28,3,250-->

## References
