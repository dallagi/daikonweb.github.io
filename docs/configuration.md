---
layout: default
title: Configuration
nav_order: 90
---

# Configuration

## Custom port
By default the server starts on port `4545` but you can specify a different one.

```kotlin
@Test
fun `start on port 8080`() {
    HttpServer(8080)
        .get("/") { _, res -> res.write("Hello") }
        .start().use {
            assertThat(get("http://localhost:8080/").text).isEqualTo("Hello")
        }
}
```
