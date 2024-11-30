---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/schema-evolution-compatibility-matrix-202404101240/","tags":["📖"],"created":"2024-04-11T20:57:45.073-05:00","updated":"2024-11-10T13:47:34.000-06:00"}
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

## References
