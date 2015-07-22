# Docker external graphdriver api.

Go handler to create external graphdriver for Docker.

## Usage

This library is designed to be integrated in your program.

1. Implement the `degraph.Driver` interface.
2. Initialize a `degraph.Hander` with your implementation.
3. Call either `ServeTCP` or `ServeUnix` from the `degraph.Handler`.

### Example using TCP sockets:

```go
  d := MyGraphDriver{}
  h := degraph.NewHandler(d)
  h.ServeTCP("test_graphdriver", ":8080")
```

### Example using Unix sockets:

```go
  d := MyGraphDriver{}
  h := degraph.NewHandler(d)
  h.ServeUnix("root", "test_graphdriver")
```

## Full example plugins

- https://github.com/hustcat/rbd-driver

## License

MIT