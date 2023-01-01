# Specification

| Status Type | HTTP Status Code | Description                                                     | Properties                      |
| ----------- | ---------------- | --------------------------------------------------------------- | ------------------------------- |
| success     | 2xx              | The request was successfully received, understood, and accepted | status, metadata, data          |
| failure     | 4xx              | The request contains bad syntax or cannot be fulfilled          | status, metadata, reason        |
| error       | 5xx              | The server failed to fulfil an apparently valid request         | status, metadata, message, code |
