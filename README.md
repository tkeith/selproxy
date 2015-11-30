# selproxy - simple, robust chromedriver proxy

selproxy acts as a drop-in replacement for the Java Selenium server when only Chrome will be used (via the chromedriver binary). The Java server tends to fail to close sessions for unknown reasons, even with a TIMEOUT parameter set, and doesn't always reliably handle many sessionat once. For my simple use case, I opted to create a simple alternative server in Python. It reliably kills sessions after 60 seconds of inactivity and uses Redis to implement session locks to ensure there are no conflicts.

The dependencies are python3-flask, python3-redis, and redis-server.
