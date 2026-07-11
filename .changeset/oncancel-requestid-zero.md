---
'@modelcontextprotocol/core-internal': patch
---

Honor `requestId: 0` in inbound `notifications/cancelled`. The previous truthiness guard dropped the notification whenever the per-instance counter's zero-based id pointed at an in-flight handler, so the first outbound request could not be cancelled by the peer. Closes #2283.
