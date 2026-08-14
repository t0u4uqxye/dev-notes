# Go HTTP Server Timeouts

Quick reference for setting sane defaults.

```go
srv := &http.Server{
    Addr:         ":8080",
    ReadTimeout:  5 * time.Second,
    WriteTimeout: 10 * time.Second,
    IdleTimeout:  60 * time.Second,
}
```

- `ReadTimeout` covers reading the request body.
- `WriteTimeout` covers writing the response.
- `IdleTimeout` is for keep-alive connections.

Use `ReadHeaderTimeout` separately if you need a stricter header limit.

Remember: these are per-connection, not per-request.